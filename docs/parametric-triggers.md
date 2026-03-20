\# Parametric Triggers for Food Delivery Partners

\*\*Platform:\*\* GigGuard  

\*\*Target Market:\*\* Mumbai Food Delivery (Zomato/Swiggy)



\---



\## What is a Parametric Trigger?



A parametric trigger is an \*\*objective, measurable event\*\* that automatically activates a payout \*\*without manual claim filing\*\*.



\*\*Example:\*\*

\-  \*\*Traditional Insurance:\*\* "It rained, I couldn't work, please approve my claim" → Manual review

\-  \*\*Parametric Insurance:\*\* Rainfall >50mm detected in your zone → Automatic ₹400 payout



\---



\## Trigger Design Principles



\### 1. Objective \& Verifiable

\- Must come from \*\*third-party data source\*\* (weather API, government alerts)

\- Cannot be self-reported by worker



\### 2. Directly Linked to Income Loss

\- Trigger must cause delivery platform orders to drop

\- Must prevent outdoor work



\### 3. Zone-Specific

\- Triggers apply only to affected pincodes

\- Worker must be registered in that zone



\### 4. Time-Bound

\- Must specify duration (e.g., "rain for ≥2 hours")

\- Avoids payouts for 10-minute drizzle



\### 5. Fraud-Resistant

\- Cross-validates with multiple data sources

\- Prevents duplicate claims



\---



\## Trigger Table for Mumbai Food Delivery



| Trigger ID | Trigger Name | Parameter | Data Source | Threshold | Min Duration | Affected Zones | Coverage Hours | Payout Amount (Silver Plan) | Frequency (per month) |

|------------|--------------|-----------|-------------|-----------|--------------|----------------|----------------|-----------------------------|----------------------|

| \*\*TR001\*\* | Heavy Monsoon Rain | Rainfall (mm/hr) | OpenWeatherMap API | ≥50 mm/hr | 2 hours | Worker's pincode ±5km | 4 hours | ₹400 | 8–12 (June–Sept) |

| \*\*TR002\*\* | Extreme Heat | Temperature (°C) | OpenWeatherMap API | ≥42°C | 4 hours | City-wide (Mumbai) | 3 hours | ₹300 | 5–8 (April–May) |

| \*\*TR003\*\* | Severe Air Pollution | AQI | AQICN API | ≥350 | 6 hours | Zone-level | 2 hours | ₹200 | 3–5 (Nov–Dec) |

| \*\*TR004\*\* | City Curfew | Government Alert | Mock API / News | Official curfew declared | Duration of curfew | Municipal zone | Full curfew duration | ₹600 | 0–2 (rare) |

| \*\*TR005\*\* | Platform App Outage | App Status | Platform Status Page Mock | Service degraded/down | ≥30 minutes | Platform-wide | 1 hour | ₹150 | 0–1 (rare) |



\---



\## Detailed Trigger Specifications



\### TR001: Heavy Monsoon Rain



\*\*Problem It Solves:\*\*  

During heavy rain, customers don't order food (safety concerns, road conditions). Workers cannot ride bikes safely.



\*\*Technical Specification:\*\*

```yaml

trigger\_id: TR001

name: "Heavy Monsoon Rain"

parameter: rainfall\_mm\_per\_hour

data\_source: 

&#x20; api: OpenWeatherMap

&#x20; endpoint: /data/2.5/weather

&#x20; field: rain.1h

threshold: 

&#x20; value: 50

&#x20; unit: mm/hr

&#x20; operator: ">="

duration:

&#x20; minimum: 2

&#x20; unit: hours

zone\_logic:

&#x20; type: pincode\_radius

&#x20; radius\_km: 5

&#x20; worker\_location\_validation: true

coverage:

&#x20; hours\_covered: 4

&#x20; payout\_calculation: 4 × hourly\_rate

payout:

&#x20; bronze: ₹300

&#x20; silver: ₹400

&#x20; gold: ₹500

frequency:

&#x20; months: \[6, 7, 8, 9]  # June–September

&#x20; expected\_events\_per\_month: 10

&#x20; peak\_hours: \[14:00-18:00, 19:00-23:00]

fraud\_prevention:

&#x20; - Check: Worker's policy active?

&#x20; - Check: Worker registered in affected pincode?

&#x20; - Check: Duplicate claim for same event?

&#x20; - Check: Worker was "online" on platform during trigger?

&#x20; - Check: Historical fraud score <0.7

```



\*\*Payout Logic:\*\*





IF (rainfall > 50mm for ≥2 hours in pincode)

AND (worker.policy.status == ACTIVE)

AND (worker.pincode in affected\_zone)

AND (no\_duplicate\_claim(worker.id, event.id))

AND (fraud\_score(worker) < 0.7)

THEN:

payout = worker.plan.hourly\_rate × 4 hours

max\_payout = worker.plan.weekly\_cap

IF payout > max\_payout:

payout = max\_payout

initiate\_transfer(worker.upi, payout)

create\_claim(worker, event, payout, status="AUTO\_APPROVED")



\*\*Example Scenario:\*\*

\- \*\*Date:\*\* July 15, 2026, 3:00 PM

\- \*\*Location:\*\* Andheri West, Mumbai (400053)

\- \*\*Weather Data:\*\* 62mm/hr rainfall from 3:00 PM to 5:30 PM (2.5 hours)

\- \*\*Affected Workers:\*\* 47 active policies in 400053 and surrounding 5km radius

\- \*\*Payout Per Worker (Silver Plan):\*\* ₹400

\- \*\*Total Payout:\*\* 47 × ₹400 = ₹18,800



\---



\### TR002: Extreme Heat



\*\*Problem It Solves:\*\*  

At temperatures >42°C, customer orders drop (food quality concerns), and workers experience severe fatigue.



\*\*Technical Specification:\*\*

```yaml

trigger\_id: TR002

name: "Extreme Heat"

parameter: temperature\_celsius

data\_source:

&#x20; api: OpenWeatherMap

&#x20; endpoint: /data/2.5/weather

&#x20; field: main.temp

threshold:

&#x20; value: 42

&#x20; unit: °C

&#x20; operator: ">="

duration:

&#x20; minimum: 4

&#x20; unit: hours

&#x20; time\_window: \[11:00-17:00]  # Peak afternoon heat

zone\_logic:

&#x20; type: city\_wide

&#x20; applies\_to: Mumbai Metropolitan Region

coverage:

&#x20; hours\_covered: 3

payout:

&#x20; bronze: ₹200

&#x20; silver: ₹300

&#x20; gold: ₹400

frequency:

&#x20; months: \[4, 5]  # April–May

&#x20; expected\_events\_per\_month: 6

```



\*\*Payout Logic:\*\*



IF (temperature ≥ 42°C for ≥4 hours between 11am–5pm)

AND (worker.city == Mumbai)

AND (worker.policy.covers\_heat == TRUE)

THEN:

payout = 3 hours × hourly\_rate



\---



\### TR003: Severe Air Pollution



\*\*Problem It Solves:\*\*  

High AQI (>350) causes health issues, visibility problems, and reduced customer demand.



\*\*Technical Specification:\*\*

```yaml

trigger\_id: TR003

name: "Severe Air Pollution"

parameter: aqi

data\_source:

&#x20; api: AQICN

&#x20; endpoint: /feed/{city}

&#x20; field: data.aqi

threshold:

&#x20; value: 350

&#x20; category: "Very Poor to Severe"

duration:

&#x20; minimum: 6

&#x20; unit: hours

zone\_logic:

&#x20; type: zone\_level

&#x20; granularity: district

coverage:

&#x20; hours\_covered: 2

payout:

&#x20; bronze: ₹150

&#x20; silver: ₹200

&#x20; gold: ₹250

frequency:

&#x20; months: \[11, 12, 1]  # Nov–Jan

&#x20; expected\_events\_per\_month: 4

```



\---



\### TR004: City Curfew / Strikes



\*\*Problem It Solves:\*\*  

Government-imposed curfews or city-wide strikes prevent all outdoor work.



\*\*Technical Specification:\*\*

```yaml

trigger\_id: TR004

name: "City Curfew"

parameter: government\_alert

data\_source:

&#x20; api: Mock News API / Government Portal

&#x20; validation: Manual admin approval (for Phase 1)

threshold:

&#x20; value: "Official curfew declared"

&#x20; proof\_required: true

duration:

&#x20; minimum: null  # Any duration

&#x20; actual\_duration: As per government order

zone\_logic:

&#x20; type: municipal\_zone

&#x20; source: Government notification

coverage:

&#x20; hours\_covered: Actual curfew duration

payout:

&#x20; calculation: min(actual\_hours × hourly\_rate, daily\_cap)

&#x20; bronze: up to ₹500

&#x20; silver: up to ₹600

&#x20; gold: up to ₹800

frequency:

&#x20; months: \[1-12]  # Any month

&#x20; expected\_events\_per\_month: 0.5 (rare)

```



\*\*Special Note:\*\* Due to rarity and severity, this trigger requires admin validation in Phase 1.



\---



\### TR005: Platform App Outage



\*\*Problem It Solves:\*\*  

When Zomato/Swiggy app crashes, workers cannot receive orders.



\*\*Technical Specification:\*\*

```yaml

trigger\_id: TR005

name: "Platform App Outage"

parameter: app\_status

data\_source:

&#x20; api: Mock Status Page (e.g., status.zomato.com)

&#x20; fallback: Twitter API (monitor @ZomatoIN for outage tweets)

threshold:

&#x20; value: "Service degraded or down"

&#x20; validation: ≥100 user complaints on social media

duration:

&#x20; minimum: 30

&#x20; unit: minutes

zone\_logic:

&#x20; type: platform\_wide

&#x20; applies\_to: All workers on affected platform

coverage:

&#x20; hours\_covered: 1

payout:

&#x20; bronze: ₹100

&#x20; silver: ₹150

&#x20; gold: ₹200

frequency:

&#x20; expected\_events\_per\_month: 0.5

```



\---



\## Trigger Monitoring System (Phase 2 Implementation)



\### Architecture Overview





┌─────────────────────────────────────────────────────┐

│ TRIGGER MONITORING ENGINE (Celery + Redis)           │

│                                                      │

│ Every 15 minutes:                                    │

│   1. Poll Weather APIs (all active pincodes)         │

│   2. Poll AQI APIs (all zones)                       │

│   3. Check News/Government APIs (city-wide)          │

│   4. Check Platform Status Pages                     │

└─────────────────────────────────────────────────────┘

↓

┌─────────────────────────────────────────────────────┐

│ TRIGGER EVALUATION ENGINE                            │

│                                                      │

│ For each data point:                                 │

│   IF threshold breached:                             │

│     - Create Event (event\_id, trigger\_id, zone)      │

│     - Query active policies in zone                  │

│     - For each policy:                               │

│         - Run fraud checks                           │

│         - Calculate payout                           │

│         - Initiate claim                             │

└─────────────────────────────────────────────────────┘

↓

┌─────────────────────────────────────────────────────┐

│ FRAUD DETECTION \& VALIDATION                        │

│                                                      │

│ Checks (automated):                                  │

│   ✓ Policy status active?                           │

│   ✓ Worker in affected zone?                        │

│   ✓ Duplicate claim?                                │

│   ✓ Within weekly claim limits?                     │

│   ✓ Anomaly score <0.7?                             │

│   ✓ Worker was "active" on platform?                │

└─────────────────────────────────────────────────────┘

↓

┌─────────────────────────────────────────────────────┐

│ PAYOUT EXECUTION ENGINE                             │

│                                                      │

│   - Calculate final payout amount                    │

│   - Call payment gateway API (Razorpay)              │

│   - Create transaction record                        │

│   - Send notification (SMS + Push)                   │

│   - Update claim status: PAID                        │

└─────────────────────────────────────────────────────┘



\---



\## API Integration Details (Phase 2/3)



\### OpenWeatherMap API



Endpoint: https://api.openweathermap.org/data/2.5/weather

Method: GET

Params:



\* lat: 19.0760 (Mumbai)

\* lon: 72.8777

\* appid: YOUR\_API\_KEY

Response Fields Used:

\* rain.1h (rainfall in last hour)

\* main.temp (temperature)

Rate Limit: 60 calls/minute (free tier)

Cost: Free for <1000 calls/day





\### AQICN API



Endpoint: https://api.waqi.info/feed/mumbai/

Method: GET

Params:



\* token: YOUR\_API\_KEY

Response Fields Used:

\* data.aqi (Air Quality Index)

Rate Limit: 1000 calls/day (free tier)

Cost: Free





\---



\## Trigger Testing Scenarios (for Demo Video)



\### Scenario 1: Heavy Rain Trigger (Most Common)

\*\*Setup:\*\*

1\. Worker "Raj" has active Silver plan (₹49/week)

2\. Registered zone: 400053 (Andheri West)

3\. Date: July 20, 2026, 3:00 PM



\*\*Trigger Event:\*\*

\- OpenWeatherMap reports: 58mm/hr rainfall at 3:00 PM

\- Duration: 3:00 PM to 5:30 PM (2.5 hours) ✓ Meets ≥2 hour threshold



\*\*System Actions:\*\*

1\. Monitoring engine detects threshold breach at 3:15 PM

2\. Creates event: `EVT\_RAIN\_400053\_20260720\_1500`

3\. Queries database: 47 active policies in zone

4\. For Raj:

&#x20;  - Policy active? ✓ Yes

&#x20;  - Zone match? ✓ Yes (400053)

&#x20;  - Duplicate? ✓ No previous claim for this event

&#x20;  - Fraud score? ✓ 0.3 (low risk)

&#x20;  - Calculate payout: 4 hours × ₹52/hr = ₹208 → Round to ₹400 (Silver plan rate)

5\. Initiate payout to Raj's UPI: ₹400

6\. Send SMS: "Heavy rain detected in Andheri. ₹400 added to your account. Claim #CLM2026072001"

7\. Claim status: \*\*PAID\*\* ✓



\*\*Timeline:\*\* Entire process completes in \*\*3–5 minutes\*\* after threshold breach.



\---



\## Constraints \& Exclusions



\### What is NOT Covered (Critical)

&#x20;\*\*Health issues\*\* (e.g., worker gets sick from rain)  

&#x20;\*\*Vehicle damage\*\* (e.g., bike breaks down in rain)  

&#x20;\*\*Accidents\*\* (e.g., worker slips and injures)  

&#x20;\*\*Personal choice\*\* (e.g., worker decides not to work)  

&#x20;\*\*Low demand\*\* (e.g., general slow day with no trigger)



\### What IS Covered

&#x20;\*\*External disruptions\*\* that prevent delivery work  

&#x20;\*\*Objectively measurable\*\* via third-party APIs  

&#x20;\*\*Loss of income\*\* (hours you cannot work)



\---



\## Success Metrics (for Phase 3 Dashboard)



\### Trigger Performance KPIs

\- \*\*Trigger Accuracy:\*\* % of events correctly detected vs. false positives

\- \*\*Payout Speed:\*\* Average time from trigger detection to payout

\- \*\*Fraud Rate:\*\* % of claims flagged/rejected

\- \*\*Loss Ratio:\*\* Total payouts / Total premiums (target: 60–70%)

\- \*\*Worker Satisfaction:\*\* % who received payout within 10 minutes



\---



\*\*Document Version:\*\* 1.0  

\*\*Last Updated:\*\* March 2026  

\*\*Next Update:\*\* After Phase 2 API integration testing

