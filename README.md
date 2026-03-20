GigGuard: Parametric Income Protection for Food Delivery Partners




**Guidewire DEVTrails 2026 Hackathon**

[![GitHub](https://img.shields.io/badge/GitHub-Repository-blue)](https://github.com/Luvagnihotri12/devtrails-gig-insurance)
[![License](https://img.shields.io/badge/License-MIT-green)](LICENSE)
[![Phase](https://img.shields.io/badge/Phase-1%3A%20Ideation-yellow)](docs/)

---

##  Table of Contents
1. [Executive Summary](#executive-summary)
2. [The Problem](#the-problem)
3. [Our Solution](#our-solution)
4. [How It Works](#how-it-works)
5. [Persona & Market](#persona--market)
6. [Parametric Triggers](#parametric-triggers)
7. [Weekly Pricing Model](#weekly-pricing-model)
8. [AI/ML Strategy](#aiml-strategy)
9. [Tech Stack](#tech-stack)
10. [Roadmap](#roadmap)
11. [Team & Submissions](#team--submissions)

---

##  Executive Summary

**Problem:** India's 2+ million food delivery partners (Zomato/Swiggy) lose 20–30% of monthly income during external disruptions (heavy rain, extreme heat, pollution, curfews) with **no financial safety net**.

**Solution:** **GigGuard** is an AI-powered parametric insurance platform that:
-  **Automatically detects** disruptions using real-time APIs (weather, pollution, news)
-  **Instantly pays** workers for lost income (within 5 minutes, no claim forms)
-  **Uses machine learning** to adjust premiums based on zone-level risk
-  **Prevents fraud** with AI anomaly detection

**Business Model:** Micro-insurance priced **weekly** (₹29–₹79/week) to match gig workers' payout cycles.

**Key Innovation:** **Parametric triggers** = Payout based on objective events (e.g., "Rain >50mm"), not manual claim investigation.

---

## The Problem

### India's Gig Economy Reality

Food delivery partners are the backbone of India's digital economy, but they face severe income volatility:

| Disruption | Frequency (Mumbai) | Income Impact | Current Solution |
|------------|-------------------|---------------|------------------|
| **Heavy Monsoon Rain** | 8–12 days/month (June–Sept) | 40–60% drop |  None |
| **Extreme Heat** | 5–8 days/month (April–May) | 20–30% drop |  None |
| **Severe Pollution** | 3–5 days/month (Nov–Dec) | 15–25% drop |  None |
| **City Curfews** | 0–2 times/month | 100% loss |  None |

### The Financial Impact

**Case Study: Raj Kumar (Swiggy Partner, Mumbai)**
- **Normal Month:** ₹22,000 earnings
- **Monsoon Month:** ₹14,500 earnings (34% loss = ₹7,500)
- **Coping Mechanism:** Borrows from moneylenders at 15–20% monthly interest
- **Result:** Debt cycle, no savings

### Why Traditional Insurance Doesn't Work

| Traditional Insurance | Why It Fails for Gig Workers |
|-----------------------|------------------------------|
| Monthly premiums | Workers paid weekly → cash flow mismatch |
| Manual claim filing | Takes days/weeks → Workers need money NOW |
| Requires documentation | Most disruptions leave no "proof" |
| Covers health/accidents | Doesn't cover **income loss from weather** |

**The Gap:** No product exists to protect gig workers against **external disruptions** causing **immediate income loss**.

---

##  Our Solution: GigGuard

### What is "Parametric" Insurance?

**Traditional Insurance:**  
"I couldn't work because of rain. Please approve my claim." → Adjuster investigates → Payout in 2 weeks

**Parametric Insurance (GigGuard):**  
Rain >50mm detected in your zone → Automatic ₹400 payout in 5 minutes → No claim form needed

### Core Principles

1. **Weekly Micro-Premiums:** ₹29–₹79/week (not monthly)
2. **Instant Payouts:** Money in UPI wallet within minutes
3. **Zero Documentation:** No claim forms, no proof required
4. **AI-Driven:** Dynamic pricing + fraud detection
5. **Objective Triggers:** Based on third-party APIs (weather, pollution)

---

##  How It Works (5-Step Process)

┌──────────────────────────────────────────────────────────────┐
│ STEP 1: Worker Buys Weekly Policy                            │
│                                                               │
│ • Open GigGuard app                                          │
│ • Enter: Platform (Zomato/Swiggy), Zone (pincode), Earnings │
│ • AI calculates personalized premium (₹49–₹68/week)         │
│ • Pay via UPI                                                │
│ • Policy active: Monday 12am – Sunday 11:59pm               │
└──────────────────────────────────────────────────────────────┘
↓
┌──────────────────────────────────────────────────────────────┐
│ STEP 2: Real-Time Trigger Monitoring (Every 15 Minutes)      │
│                                                               │
│ System polls:                                                │
│   - OpenWeatherMap API (rainfall, temperature)               │
│   - AQICN API (air quality index)                            │
│   - News APIs (curfew alerts)                                │
│   - Platform Status Pages (app outages)                      │
│                                                               │
│ IF threshold breached → Create Event                         │
└──────────────────────────────────────────────────────────────┘
↓
┌──────────────────────────────────────────────────────────────┐
│ STEP 3: Automated Fraud Detection (AI)                       │
│                                                               │
│ For each affected worker:                                    │
│   ✓ Policy status active?                                    │
│   ✓ Worker registered in affected zone?                      │
│   ✓ Duplicate claim for same event?                          │
│   ✓ Within weekly claim limits (max 2–4 events)?            │
│   ✓ Anomaly score <0.7? (Isolation Forest algorithm)        │
│   ✓ Worker was "online" on platform during disruption?      │
│                                                               │
│ Result: 98% auto-approved, 2% flagged for manual review      │
└──────────────────────────────────────────────────────────────┘
↓
┌──────────────────────────────────────────────────────────────┐
│ STEP 4: Instant Payout Calculation & Transfer                │
│                                                               │
│ Payout = Covered Hours × Worker's Insured Hourly Rate       │
│ Example: 4 hours × ₹55/hr = ₹220 → Round to ₹400 (plan rate)│
│                                                               │
│ Transfer via Razorpay API to worker's UPI                    │
│ Timeline: <5 minutes from trigger detection                  │
└──────────────────────────────────────────────────────────────┘
↓
┌──────────────────────────────────────────────────────────────┐
│ STEP 5: Worker Notification & Claim Record                   │
│                                                               │
│ SMS: "Heavy rain detected in Andheri. ₹400 added to wallet."│
│ Push Notification: "Claim #CLM2026072001 PAID ✓"            │
│ In-app: Full claim details with event proof                  │
└──────────────────────────────────────────────────────────────┘

---

##  Persona & Market

### Target Persona: Food Delivery Partner (Mumbai)

**Profile:**
- **Name:** Raj Kumar (representative)
- **Age:** 28 years
- **Platform:** Swiggy (also applicable to Zomato)
- **Vehicle:** Honda Activa (scooter)
- **Working Hours:** 8–10 hrs/day, 6 days/week
- **Shift Timing:** 11am–2pm (lunch), 6pm–11pm (dinner)
- **Monthly Earnings:** ₹18,000–₹24,000
- **Payment Cycle:** Weekly (every Friday)
- **Tech:** Android phone, uses UPI daily

**Pain Points:**
1. **Income volatility:** One rainy day = ₹500–800 loss
2. **No savings buffer:** Lives paycheck to paycheck
3. **Forced to work in unsafe conditions:** Rain, extreme heat, pollution
4. **Zero financial safety net:** No insurance, no emergency fund
5. **Debt dependence:** Borrows at high interest during disruptions

### Market Size (Mumbai)

| Metric | Value |
|--------|-------|
| Total food delivery partners | ~50,000 |
| Active daily | ~35,000 (70%) |
| Full-time (target segment) | ~25,000 (50%) |
| **Addressable Market (10% adoption)** | **2,500 workers** |
| **Revenue Potential (₹49/week avg)** | **₹122,500/week** |
| **Annual Revenue (conservative)** | **₹6.37M** |

---

##  Parametric Triggers

### Trigger Summary Table

| Trigger | Data Source | Threshold | Payout (Silver Plan) | Frequency (Mumbai) |
|---------|-------------|-----------|----------------------|--------------------|
| **Heavy Rain** | OpenWeatherMap | >50mm/hr for ≥2 hours | ₹400 | 8–12 days/month (monsoon) |
| **Extreme Heat** | OpenWeatherMap | >42°C for ≥4 hours | ₹300 | 5–8 days/month (summer) |
| **Severe Pollution** | AQICN API | AQI >350 for ≥6 hours | ₹200 | 3–5 days/month (winter) |
| **City Curfew** | News API / Mock | Official curfew declared | ₹600 | 0–2 times/month (rare) |
| **App Outage** | Platform Status | Service down ≥30 mins | ₹150 | 0–1 time/month (rare) |

### Example: Heavy Rain Trigger (Most Common)

**Scenario:**
- **Date:** July 15, 2026, 3:00 PM
- **Location:** Andheri West, Mumbai (Pincode 400053)
- **Weather Data:** 58mm/hr rainfall from 3:00 PM to 5:30 PM (2.5 hours)

**System Actions:**
1. **3:15 PM:** Monitoring engine detects threshold breach
2. **3:16 PM:** Creates event `EVT_RAIN_400053_20260715_1500`
3. **3:17 PM:** Queries database → Finds 47 active policies in zone
4. **3:18 PM:** For each worker:
   - Validates policy status ✓
   - Checks zone match ✓
   - Runs fraud detection (anomaly score 0.3) ✓
   - Calculates payout: ₹400
5. **3:20 PM:** Initiates 47 payouts via Razorpay API
6. **3:22 PM:** All workers receive SMS + Push notification
7. **3:25 PM:** Money in workers' UPI wallets ✓

**Total Time:** **10 minutes** from rain detection to payout

---

##  Weekly Pricing Model

### Why Weekly? (Not Monthly)

| Factor | Weekly Model | Monthly Model |
|--------|--------------|---------------|
| **Commitment** | 7 days (low risk to try) | 30 days (high barrier) |
| **Cash Flow Alignment** | Matches Friday payout | Disconnected from earnings cycle |
| **Flexibility** | Can upgrade/downgrade each week | Locked in for month |
| **Affordability Perception** | ₹49/week = 1 delivery order | ₹200/month = feels expensive |
| **Adoption Rate** | High (50–70%) | Low (20–30%) |

### Pricing Formula


Weekly Premium = Base Plan Price
+ Risk Load (AI-calculated)
+ Seasonality Adjustment
- Loyalty Discount

### Plan Tiers

####  Bronze Plan: ₹29/week
- **For:** Part-time riders (3–5 days/week)
- **Covers:** Heavy rain + Extreme heat
- **Weekly Cap:** ₹500 payout max
- **Max Events:** 2/week

####  Silver Plan: ₹49/week **(RECOMMENDED)**
- **For:** Full-time riders (5–6 days/week)
- **Covers:** Rain + Heat + Pollution + Curfew
- **Weekly Cap:** ₹1,200 payout max
- **Max Events:** 4/week

####  Gold Plan: ₹79/week
- **For:** High-volume, experienced riders
- **Covers:** All 5 triggers (includes app outages)
- **Weekly Cap:** ₹2,000 payout max
- **Max Events:** Unlimited

### Dynamic Pricing Example (Silver Plan)

**Worker A: Safe Zone, Non-Monsoon**

Base Price:        ₹49
Risk Load (AI):    -₹5  (low disruption history in zone)
Seasonality:       ₹0   (March = stable month)
Loyalty Discount:  -₹5  (renewed 4 weeks in a row)
───────────────────────
Final Price:       ₹39/week ✓

**Worker B: Flood-Prone Zone, Monsoon Peak**

Base Price:        ₹49
Risk Load (AI):    +₹10 (high flood risk in Kurla zone)
Seasonality:       +₹10 (July = peak monsoon)
Loyalty Discount:  ₹0   (new customer)
───────────────────────
Final Price:       ₹69/week

---

## 🤖 AI/ML Strategy

### Use Case 1: Dynamic Premium Calculation

**Algorithm:** XGBoost Gradient Boosting  
**Goal:** Predict disruption probability for next week

**Input Features:**
```python
features = [
    'pincode',
    'historical_rainfall_12_weeks',
    'historical_temperature_12_weeks',
    'historical_aqi_12_weeks',
    'worker_platform_experience_months',
    'worker_avg_daily_hours',
    'worker_claim_history_count',
    'zone_flood_risk_score',  # from municipal data
    'month_of_year',
    'is_monsoon_season',
    'day_of_week'
]
```

**Output:**

risk_score ∈ [0, 1]
Mapping to Premium Adjustment:
risk_score = 0.2 → Discount ₹9/week
risk_score = 0.5 → No change
risk_score = 0.8 → Increase ₹9/week

**Training Data:**
- Weather APIs: Historical data 2023–2025 (OpenWeather)
- Claim data: First 4 weeks of Phase 2 (baseline)
- Mumbai municipal flood maps

**Phase 2 Implementation:**
- Week 1–4: Collect baseline data
- Week 5: Train XGBoost model
- Week 6: Deploy as API microservice (`/calculate-premium`)

---

### Use Case 2: Fraud Detection

**Algorithm:** Isolation Forest (Anomaly Detection)  
**Goal:** Flag suspicious claims before payout

**Features:**
```python
fraud_features = [
    'claims_last_7_days',
    'claims_last_30_days',
    'time_since_last_claim_hours',
    'payout_amount_vs_avg',
    'gps_distance_from_registered_zone_km',
    'worker_was_online_on_platform',  # from platform API
    'claim_timestamp_vs_usual_working_hours'
]
```

**Output:**

anomaly_score ∈ [0, 1]
Decision Logic:
score < 0.5  → AUTO_APPROVE (98% of cases)
score 0.5–0.7 → FLAG_FOR_REVIEW (1.5% of cases)
score > 0.7  → REJECT/ESCALATE (0.5% of cases)

**Example Fraud Scenarios Detected:**
1. **GPS Spoofing:** Worker claims rain trigger but GPS shows 50km away from affected zone
2. **Duplicate Claims:** Same worker tries to claim twice for same rain event
3. **Anomalous Pattern:** Worker has 10 claims in 2 weeks (avg is 2)
4. **Platform Inactivity:** Claims "couldn't work" but was never online during disruption
