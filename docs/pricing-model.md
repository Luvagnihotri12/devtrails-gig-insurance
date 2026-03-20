\# Weekly Pricing Model for Food Delivery Insurance

\*\*Product:\*\* GigGuard Income Protection  

\*\*Market:\*\* Mumbai Food Delivery Partners



\---



\## Why Weekly Pricing?



\### Traditional Insurance Problem

\- Monthly premiums: ₹200–300/month

\- Workers paid weekly (Friday/Saturday)

\- By week 3, premium feels "too far away"

\- High churn after first month



\### GigGuard Solution

\- \*\*Weekly premiums:\*\* ₹29–₹79/week

\- Aligns with worker payout cycle

\- Can upgrade/downgrade each week

\- Low commitment → higher adoption



\---



\## Pricing Formula





Weekly Premium = Base Plan Price

\+ Risk Load Adjustment

\+ Seasonality Adjustment

\- Loyalty Discount



\### Components Breakdown



\#### 1. Base Plan Price

Fixed price based on coverage tier:

\- \*\*Bronze:\*\* ₹29/week

\- \*\*Silver:\*\* ₹49/week

\- \*\*Gold:\*\* ₹79/week



\#### 2. Risk Load Adjustment

AI-calculated based on zone's historical disruption frequency:





Risk Score ∈ \[0, 1] (calculated by ML model in Phase 2)

Risk Load = (Risk Score - 0.5) × 30

Examples:



\* Risk Score = 0.2 (safe zone)  → Load = -9  → Discount ₹9

\* Risk Score = 0.5 (average)    → Load = 0   → No change

\* Risk Score = 0.8 (flood-prone)→ Load = +9  → Increase ₹9





\#### 3. Seasonality Adjustment

Mumbai monsoon pattern:



| Month | Disruption Risk | Adjustment |

|-------|-----------------|------------|

| Jan–Mar | Low | ₹0 |

| Apr–May | Medium (heat) | +₹5 |

| Jun–Sep | High (monsoon) | +₹10 |

| Oct–Dec | Medium (pollution) | +₹5 |



\#### 4. Loyalty Discount

Rewards for claim-free renewals:



| Consecutive Weeks | Discount |

|-------------------|----------|

| 1–3 weeks | ₹0 |

| 4–7 weeks | -₹5 |

| 8–11 weeks | -₹8 |

| 12+ weeks | -₹10 |



\---



\## Plan Details



\### Bronze Plan: ₹29/week



\*\*Target User:\*\* Part-time, casual delivery partners



| Feature | Value |

|---------|-------|

| \*\*Base Weekly Premium\*\* | ₹29 |

| \*\*Weekly Payout Cap\*\* | ₹500 |

| \*\*Covered Triggers\*\* | Heavy Rain, Extreme Heat |

| \*\*Max Events/Week\*\* | 2 |

| \*\*Hourly Rate (Assumed)\*\* | ₹50/hr |

| \*\*Total Coverage/Week\*\* | Up to 10 hours (₹500) |



\*\*Example Pricing Scenarios:\*\*



\*\*Scenario A: Safe Zone, Non-Monsoon\*\*

\- Base: ₹29

\- Risk Load (score 0.3): (0.3-0.5)×30 = -6 → -₹6

\- Season (March): ₹0

\- Loyalty (new): ₹0

\- \*\*Final Price: ₹23/week\*\*



\*\*Scenario B: Flood-Prone, Monsoon Peak\*\*

\- Base: ₹29

\- Risk Load (score 0.75): (0.75-0.5)×30 = +7.5 → +₹8

\- Season (July): +₹10

\- Loyalty (new): ₹0

\- \*\*Final Price: ₹47/week\*\*



\---



\### Silver Plan: ₹49/week (RECOMMENDED)



\*\*Target User:\*\* Full-time delivery partners



| Feature | Value |

|---------|-------|

| \*\*Base Weekly Premium\*\* | ₹49 |

| \*\*Weekly Payout Cap\*\* | ₹1,200 |

| \*\*Covered Triggers\*\* | Rain, Heat, Pollution, Curfew |

| \*\*Max Events/Week\*\* | 4 |

| \*\*Hourly Rate (Assumed)\*\* | ₹55/hr |

| \*\*Total Coverage/Week\*\* | Up to 22 hours (₹1,200) |



\*\*Example Pricing Scenarios:\*\*



\*\*Scenario A: Average Zone, Clear Month\*\*

\- Base: ₹49

\- Risk Load (score 0.5): ₹0

\- Season (October): +₹5

\- Loyalty (6 weeks): -₹5

\- \*\*Final Price: ₹49/week\*\*



\*\*Scenario B: High-Risk Zone, Monsoon\*\*

\- Base: ₹49

\- Risk Load (score 0.8): (0.8-0.5)×30 = +9 → +₹9

\- Season (August): +₹10

\- Loyalty (new): ₹0

\- \*\*Final Price: ₹68/week\*\*



\---



\### Gold Plan: ₹79/week



\*\*Target User:\*\* High-volume, experienced riders



| Feature | Value |

|---------|-------|

| \*\*Base Weekly Premium\*\* | ₹79 |

| \*\*Weekly Payout Cap\*\* | ₹2,000 |

| \*\*Covered Triggers\*\* | All 5 (Rain, Heat, Pollution, Curfew, Outage) |

| \*\*Max Events/Week\*\* | Unlimited |

| \*\*Hourly Rate (Assumed)\*\* | ₹65/hr |

| \*\*Total Coverage/Week\*\* | Up to 31 hours (₹2,000) |



\*\*Example Pricing:\*\*



\*\*Scenario: High-Risk, Monsoon, Loyal Customer\*\*

\- Base: ₹79

\- Risk Load (score 0.7): (0.7-0.5)×30 = +6 → +₹6

\- Season (July): +₹10

\- Loyalty (12 weeks): -₹10

\- \*\*Final Price: ₹85/week\*\*



\---



\## Financial Viability Analysis



\### Assumptions (Silver Plan, 1000 Workers, 1 Week)



\*\*Income Side:\*\*



Average premium (accounting for adjustments): ₹54/week

Workers: 1000

Weekly Revenue: ₹54,000



\*\*Expense Side (Payouts):\*\*



\*\*Normal Week (No Major Disruptions):\*\*

\- 10% face light rain trigger: 100 × ₹400 = ₹40,000

\- 5% face heat trigger: 50 × ₹300 = ₹15,000

\- Total Payout: ₹55,000

\- \*\*Loss Ratio: 55,000 / 54,000 = 102%\*\*  Slight loss



\*\*Heavy Monsoon Week:\*\*

\- 40% face rain trigger: 400 × ₹400 = ₹160,000

\- 10% face pollution: 100 × ₹200 = ₹20,000

\- Total Payout: ₹180,000

\- \*\*Loss Ratio: 180,000 / 54,000 = 333%\*\*  Unsustainable



\### Solution: Event Caps \& Premium Adjustments



\*\*With Event Cap (Max 2 claims/worker/week):\*\*

\- Heavy week: Actual claims = 400, but cap at 2 per worker

\- Effective claims: 400 workers × 1.5 avg claims = 600 total claim instances

\- Payout: 600 × ₹350 avg = ₹210,000

\- \*\*Still high at 389% loss ratio\*\*



\*\*Revised Approach:\*\*

1\. \*\*Increase monsoon premium:\*\* +₹15 instead of +₹10

2\. \*\*Reduce payout per event:\*\* ₹400 → ₹350 for rain

3\. \*\*Strict event caps:\*\* 2 per week max

4\. \*\*Pool diversification:\*\* Expand to less risky zones



\*\*Revised Heavy Week:\*\*

\- Premium (monsoon adjusted): ₹59/week

\- Revenue: 1000 × ₹59 = ₹59,000

\- Payouts (capped): ₹210,000 × 0.6 (with caps) = ₹126,000

\- \*\*Loss Ratio: 126,000 / 59,000 = 214%\*\* (Better, but still high)



\*\*Long-term Strategy:\*\*

\- Target \*\*70% loss ratio\*\* across full year

\- Accept 150–200% in monsoon months

\- Compensate with 30–40% in dry months

\- Build reserves during April–May (low claim months)



\---



\## Competitor Pricing Comparison



| Provider | Product | Premium | Coverage | Payout Speed |

|----------|---------|---------|----------|--------------|

| \*\*Acko\*\* | Two-wheeler insurance | ₹500–800/month | Vehicle damage | 3–5 days |

| \*\*Digit\*\* | Gig worker health | ₹300/month | Medical bills | 7–14 days |

| \*\*Onsurity\*\* | Health insurance | ₹400/month | Hospitalization | 5–7 days |

| \*\*GigGuard (Ours)\*\* | Income protection | ₹49/week (₹196/month) | Lost wages | \*\*5 minutes\*\* ✓ |



\*\*Key Differentiator:\*\* Instant payout + parametric triggers (no claim forms)



\---



\## Pricing Psychology for Gig Workers



\### What Works

&#x20;\*\*₹49/week\*\* = Cost of 1 delivery order → Feels affordable  

&#x20;\*\*Weekly renewal\*\* = Low commitment, easy to try  

&#x20;\*\*Instant payout\*\* = Immediate value demonstration  

&#x20;\*\*Clear triggers\*\* = "If rain >50mm, get ₹400" → Simple to understand



\### What Doesn't Work

&#x20;\*\*₹200/month\*\* = Feels expensive upfront  

&#x20;\*\*Annual plans\*\* = Too long a commitment  

&#x20;\*\*Complex terms\*\* = Workers won't read fine print  

&#x20;\*\*Delayed payouts\*\* = "Insurance is a scam" perception



\---



\## Dynamic Pricing (AI/ML - Phase 2)



\### Risk Scoring Model (Planned)



\*\*Input Features:\*\*

```python

features = \[

&#x20;   'pincode',

&#x20;   'historical\_rainfall\_12\_weeks',

&#x20;   'historical\_aqi\_12\_weeks',

&#x20;   'worker\_avg\_daily\_hours',

&#x20;   'worker\_platform\_experience\_months',

&#x20;   'worker\_claim\_history',

&#x20;   'zone\_flood\_risk\_score',

&#x20;   'month\_of\_year',

&#x20;   'is\_monsoon\_season'

]

```



\*\*Model:\*\*



Algorithm: Gradient Boosting (XGBoost)

Target Variable: disruption\_probability\_next\_week ∈ \[0, 1]

Training Data: 12 months of historical weather + claims

Prediction:

risk\_score = model.predict(worker\_features)

risk\_load = (risk\_score - 0.5) × 30

weekly\_premium = base\_price + risk\_load + seasonality - loyalty



\*\*Example Output:\*\*



Worker: Raj Kumar

Pincode: 400053 (Andheri West)

Month: July 2026

Platform Experience: 18 months

Claim History: 2 claims in last 12 weeks

Zone Flood Risk: High (0.75)

Model Output:

risk\_score = 0.72

risk\_load = (0.72 - 0.5) × 30 = +₹6.6 → Round to +₹7

base\_price = ₹49

seasonality = +₹10 (monsoon)

loyalty = -₹5 (4 weeks renewal)

Final Premium: ₹49 + 7 + 10 - 5 = ₹61/week



\---



\## Affordability Check



\### Worker's Weekly Budget



Weekly Earnings (Average): ₹1,200

Expenses:



\* Fuel: ₹750

\* Food: ₹500

\* Phone: ₹125

\* Misc: ₹200

Total Expenses: ₹1,575

Deficit: -₹375 (often borrow)



Insurance Premium (Silver): ₹49

As % of earnings: 4.1% (acceptable)

As % of disposable income: N/A (negative disposable income)

Key Insight: Workers operate on thin margins.

Premium must be ≤5% of weekly earnings to be viable.



\### Price Sensitivity Analysis



\*\*Willingness to Pay (Hypothetical Survey):\*\*

\- ₹29/week: 70% would buy

\- ₹49/week: 50% would buy (optimal)

\- ₹79/week: 25% would buy

\- ₹99/week: 10% would buy



\*\*Optimal Price Point:\*\* ₹49/week for Silver (balance of adoption × revenue)



\---



\## Renewal \& Churn Strategy



\### Auto-Renewal Logic



IF worker.balance >= next\_week\_premium:

auto\_renew()

send\_notification("Policy renewed for ₹X. Active until \[date]")

ELSE:

send\_reminder\_24h\_before("Low balance. Add ₹X to continue coverage")

IF still\_no\_balance:

policy.status = "LAPSED"

send\_notification("Policy expired. Reactivate anytime.")



\### Win-Back Campaign

\- Lapsed for 1 week: SMS with 10% discount

\- Lapsed for 2 weeks: Call from support

\- Lapsed for 4 weeks: Re-onboarding offer (first week free)



\---



\## Phase 1 Summary



\*\*For Submission:\*\*

1\.  Weekly pricing model defined

2\.  Three plan tiers (Bronze/Silver/Gold)

3\.  Dynamic pricing formula explained

4\.  Financial viability analyzed

5\.  Competitive positioning clear



\*\*Phase 2 Implementation:\*\*

\- Build XGBoost risk scoring model

\- Integrate real-time premium calculation

\- A/B test pricing (₹49 vs. ₹54 vs. ₹59)

\- Monitor loss ratios weekly

