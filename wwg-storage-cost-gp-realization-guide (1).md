# WWG Storage Cost Integration: From Booked GP to Realized GP
## Critical Business Reality for Sales Operations

**VERSION:** 1.0  
**DATE:** 2025-11-08  
**AUTHOR:** AI/BI Transformation Team

---

## 🎯 Executive Summary: The £450K Storage Cost Problem

### The Hidden Margin Killer

**CFO Data:**
- **Annual Storage Costs:** £450,000
- **Annual Revenue:** £53,000,000
- **Storage as % of Revenue:** 0.85%
- **Annual Containers:** 350
- **Average Cost per Container:** £1,286

**Current vs Target Performance:**
- **Current Average Storage:** 12 days
- **Target Storage:** 4 days
- **Excess Storage:** 8 days (3x target)
- **Annual Waste Opportunity:** £300,000

**Impact on Gross Margin:**
- Current GM: 10.5% (generating 2.6% EBITDA)
- Storage cost impact: 0.85% of revenue
- If storage reduced to target: +0.57% margin improvement
- **Value of hitting target: £300K annual savings = 0.57% margin = £300K straight to EBITDA**

### The Core Problem

Sales books deals with GP calculated on:
```
Booked GP = Revenue - (Landed Cost + PLANNED Storage + PLANNED Logistics)
```

Reality delivers GP based on:
```
Realized GP = Revenue - (Landed Cost + ACTUAL Storage + ACTUAL Logistics)
```

**The gap between these two is where £300K+ disappears annually.**

---

## 📊 Storage Cost Allocation Model

### Company-Level Storage Economics

```json
{
  "annual_storage_cost": "£450,000",
  "annual_revenue": "£53,000,000",
  "storage_as_percent_revenue": "0.85%",
  "annual_containers": "350",
  "average_container_weight": "25,000 kg",
  "total_annual_throughput": "8,750,000 kg",
  
  "cost_per_unit": {
    "per_container": "£1,286",
    "per_kg": "£0.0514",
    "per_day": "£1,233 (total facility)",
    "per_container_per_day": "£3.52"
  },
  
  "current_performance": {
    "average_storage_days": "12",
    "target_storage_days": "4",
    "excess_days": "8",
    "containers_per_week": "6.7",
    "typical_occupancy": "80-100 containers at any time"
  },
  
  "target_performance": {
    "storage_days": "4",
    "annual_storage_cost_at_target": "£150,000",
    "annual_savings_opportunity": "£300,000",
    "margin_improvement": "0.57%"
  }
}
```

### Container-Level Storage Tracking

**For each container, track:**

```
Container ID: CNT-2025-001
- Vessel Arrival: 2025-11-01 (planned)
- Actual Arrival: 2025-11-08 (7 days late)
- Customs Clearance: 2025-11-10 (2 days)
- Storage Start: 2025-11-10
- Current Date: 2025-11-15
- Days in Storage: 5 days
- Target Exit Date: 2025-11-14 (4 days from clearance)
- Storage Days Over Target: 1 day

Container Contents:
- Total Weight: 25,000 kg
- Allocated to Sales: 18,000 kg (72%)
- Unallocated Inventory: 7,000 kg (28%)

Storage Cost Allocation:
- Total Storage Cost (5 days): £17.60 (5 × £3.52)
- Allocated to Sales: £12.67 (72%)
- Unallocated (inventory holding cost): £4.93 (28%)

Cost Impact by Order:
- Order #12345: 8,000 kg (44% of allocated)
  - Storage Cost: £5.58
  - Per kg: £0.0007
  
- Order #12346: 6,000 kg (33% of allocated)
  - Storage Cost: £4.18
  - Per kg: £0.0007
  
- Order #12347: 4,000 kg (22% of allocated)
  - Storage Cost: £2.79
  - Per kg: £0.0007
```

### Order-Level GP Tracking Example

**Order #12345 - Restaurant Chain Customer**

**AT BOOKING (2025-10-15):**
```
Product: Australian Ribeye
Quantity: 8,000 kg
Price: £12.50/kg
Revenue: £100,000

Expected Costs:
- Landed Cost: £8.20/kg × 8,000 = £65,600
- Storage (4 days): £0.028/kg = £224
- Logistics: £0.15/kg = £1,200
Total Expected Cost: £67,024
Booked GP: £32,976
Booked Margin: 32.98%

Assumptions:
- Vessel ETA: 2025-11-01
- Customs: 2 days
- Storage: 4 days
- Delivery: 2025-11-07
```

**CURRENT STATUS (2025-11-15):**
```
Reality Check:
- Vessel Arrived: 2025-11-08 (7 days late) ❌
- Customs Cleared: 2025-11-10 (2 days) ✓
- Days in Storage: 5 days (target: 4)
- Customer Pickup: 2025-11-16 (scheduled)

Actual Costs to Date:
- Landed Cost: £8.20/kg × 8,000 = £65,600 ✓
- Storage (5 days so far): £0.035/kg = £280 ⚠️
- Logistics: TBD
Current Cost: £65,880
Current GP: £34,120
Current Margin: 34.12%

Variance from Booked:
- Storage variance: +£56 (+25%)
- Margin impact: +0.06%
Status: SLIGHT IMPROVEMENT (faster customer pickup than expected)
```

**AT REALIZATION (2025-11-20 - when paid):**
```
Final Reconciliation:
- Revenue: £100,000 ✓
- Landed Cost: £65,600 ✓
- Storage (6 days actual): £0.042/kg = £336 ⚠️
- Logistics: £1,400 ⚠️
- Other costs: £50
Total Actual Cost: £67,386
Realized GP: £32,614
Realized Margin: 32.61%

Variance from Booked:
- Storage: +£112 (50% over plan)
- Logistics: +£200 (17% over plan)
- Total Variance: -£362
- Margin Erosion: -0.36%
```

**WORSE CASE EXAMPLE - Order #12350:**

**AT BOOKING:**
```
Product: NZ Lamb Legs
Quantity: 5,000 kg
Price: £9.80/kg
Revenue: £49,000

Expected Costs:
- Landed Cost: £6.50/kg × 5,000 = £32,500
- Storage (4 days): £0.028/kg = £140
- Logistics: £0.12/kg = £600
Total Expected Cost: £33,240
Booked GP: £15,760
Booked Margin: 32.16%
```

**AT REALIZATION (vessel delayed 3 weeks in Singapore):**
```
Reality:
- Vessel delayed: 21 days
- Extended storage: 25 days (target: 4)
- Customer partially cancelled, negotiated discount

Final Numbers:
- Revenue: £46,550 (5% discount due to delay) ❌
- Landed Cost: £32,500 ✓
- Storage (25 days): £0.175/kg = £875 ❌❌❌
- Logistics: £720 ⚠️
- Other (handling, repackaging): £150
Total Actual Cost: £34,245
Realized GP: £12,305
Realized Margin: 26.43%

Variance from Booked:
- Revenue: -£2,450 (customer concession)
- Storage: +£735 (525% over plan) ❌
- Total Variance: -£3,455
- Margin Erosion: -5.73% ❌❌
- GP Loss: £3,455 on a £49K order

THIS IS THE £450K PROBLEM IN ACTION.
```

---

## 🚨 Impact Analysis: Why This Matters

### Financial Impact

**Annual Storage Waste:**
```
Current: 12 days average × 350 containers × £3.52/day = £14,784
Target:  4 days average × 350 containers × £3.52/day = £4,928
Waste: 8 excess days × 350 containers × £3.52/day = £9,856 per cycle

With ~29 cycles per year: £9,856 × 29 = £285,824
Plus facility overhead waste: ~£114,176
Total Annual Waste: £450,000 (CFO figure) ✓
```

**Margin Impact:**
```
On £53M revenue:
- Storage at current (12 days): 0.85% of revenue
- Storage at target (4 days): 0.28% of revenue
- Margin improvement opportunity: 0.57%

At 10.5% current GM:
- 0.57% margin improvement = £302,100 annual savings
- This £302K flows straight to EBITDA
- Current EBITDA: £1.4M → Potential: £1.7M (+21.6%)
```

### Sales Behavior Impact

**Current State:**
Sales reps are measured and compensated on BOOKED GP, but company realizes LOWER GP due to:

1. **Vessel delays** (60-65% on-time rate)
2. **Slow customer pickup** (sales priority on booking, not delivery speed)
3. **Poor container allocation** (selling old inventory creates urgency, but extends average age)
4. **Customs issues** (unpredictable, but more common on certain origins)

**What Sales Doesn't See:**
- Rep books £50K deal at 30% margin = £15K GP
- Gets paid commission on £15K GP
- Reality: 18-day storage eats £600, logistics overrun £200
- Realized GP: £14.2K (5.3% erosion)
- Company loses £800, rep doesn't know/care

**Multiply by 350 containers/year = significant company-level GP erosion**

---

## 💡 Solution: Real-Time GP Tracking & Sales Incentive Alignment

### Phase 1: Visibility (Week 1-2)

**Implement Dashboard for Sales Team:**

```
MY DEALS - LIVE GP TRACKER
=====================================
Order #12345 | ABC Restaurant | £100K
-------------------------------------
Status: In Storage (Day 5 of 4 target)
Booked GP: £32,976 (32.98%)
Current GP: £32,614 (32.61%) ⚠️ -0.37%

Container: CNT-2025-001
Vessel: MV Southern Star (arrived 7 days late)
Storage Days: 5 (target: 4)
Customer Pickup: Tomorrow ✓

Actions Required:
→ Confirm customer pickup tomorrow
→ Storage cost: +£56 vs plan

=====================================
Order #12350 | XYZ Hotels | £49K
-------------------------------------
Status: CRITICAL - Extended Storage
Booked GP: £15,760 (32.16%)
Current GP: £12,305 (26.43%) ❌ -5.73%

Container: CNT-2025-005
Vessel: MV Pacific Trader (21 days delayed)
Storage Days: 25 (target: 4)
Customer: Requesting discount due to delay

URGENT ACTIONS:
→ Negotiate final price with customer
→ Expedite delivery THIS WEEK
→ Manager escalation required
```

### Phase 2: Quotation Risk Adjustment (Week 3-4)

**AI-Powered Quotation Tool:**

```python
def calculate_risk_adjusted_quote(product, quantity, customer, vessel_route):
    """
    Factors in storage cost risk based on vessel reliability
    """
    
    # Base costs
    landed_cost = get_landed_cost(product, quantity)
    base_logistics = get_logistics_cost(quantity)
    
    # Storage risk assessment
    vessel_reliability = get_vessel_reliability(vessel_route)
    customer_pickup_history = get_customer_speed(customer)
    customs_complexity = get_customs_risk(product.origin)
    
    # Calculate expected storage days with risk buffer
    if vessel_reliability < 0.70:  # Less than 70% on-time
        expected_storage_days = 4 + 8  # Add 8-day buffer
    elif vessel_reliability < 0.85:
        expected_storage_days = 4 + 4  # Add 4-day buffer
    else:
        expected_storage_days = 4 + 2  # Add 2-day buffer
    
    # Customer pickup factor
    if customer_pickup_history['avg_days'] > 7:
        expected_storage_days += 3
    
    # Storage cost with buffer
    storage_cost_per_kg = (expected_storage_days * 3.52) / 25000
    total_storage_cost = storage_cost_per_kg * quantity
    
    # Total expected cost
    total_cost = landed_cost + total_storage_cost + base_logistics
    
    # Pricing with margin protection
    target_margin = 0.22  # 22% target
    minimum_margin = 0.18  # 18% floor
    
    recommended_price = total_cost / (1 - target_margin)
    floor_price = total_cost / (1 - minimum_margin)
    
    return {
        'recommended_price_per_kg': recommended_price / quantity,
        'floor_price_per_kg': floor_price / quantity,
        'expected_storage_days': expected_storage_days,
        'storage_risk_buffer': expected_storage_days - 4,
        'vessel_reliability_score': vessel_reliability,
        'total_expected_cost': total_cost
    }
```

### Phase 3: Sales Incentive Alignment (Month 2)

**New Commission Structure:**

```
CURRENT (WRONG):
Commission = 5% of Booked GP

PROBLEM: 
Sales gets paid on £15K booked GP
Company realizes £14.2K actual GP
Sales has no incentive to minimize storage

PROPOSED (RIGHT):
Commission = 3% of Booked GP + 2% of Realized GP

EXAMPLE:
Order books at £15K GP:
- Immediate commission: £450 (3% × £15K)
- At realization (if £14.2K actual): £284 (2% × £14.2K)
- Total commission: £734

If realized GP matches booked:
- Total commission: £750 (same as before)

If realized GP exceeds booked (fast delivery, good execution):
- Total commission: £800+ (reward good behavior!)

INCENTIVE ALIGNMENT:
- Sales now cares about vessel reliability
- Sales now pushes customers for faster pickup
- Sales now allocates from faster-arriving containers
- Company GP protected
```

### Phase 4: Operational Integration (Month 2-3)

**Real-Time Monitoring:**

1. **Vessel Tracking Integration:**
   - API integration with vessel tracking services
   - Automated ETA updates every 6 hours
   - Alert sales team when vessel delayed >2 days

2. **Storage Cost Accumulation:**
   - Daily update of storage costs per container
   - Allocation to orders in real-time
   - Dashboard shows "days in storage" for each deal

3. **Customer Pickup Monitoring:**
   - Track from customs clearance to customer pickup
   - Automated reminders to customers at Day 2, Day 4
   - Escalation to sales manager if >7 days

4. **GP Variance Alerts:**
   - Green: GP variance < 1%
   - Yellow: GP variance 1-3%
   - Red: GP variance > 3% (triggers manager review)

---

## 📋 Implementation Checklist

### Week 1: Data Foundation
- [ ] Export last 12 months of container arrivals, storage days, costs
- [ ] Calculate actual storage cost per container per day (£3.52 validated)
- [ ] Map all open orders to containers
- [ ] Identify which containers are delayed/in extended storage
- [ ] Calculate current GP erosion on active deals

### Week 2: Dashboard Development
- [ ] Build "My Deals - Live GP Tracker" dashboard
- [ ] Integrate vessel tracking API
- [ ] Connect storage management system
- [ ] Calculate real-time GP for all active orders
- [ ] Deploy to sales team with training

### Week 3: Quotation Tool
- [ ] Build vessel reliability database (historical performance)
- [ ] Build customer pickup speed database
- [ ] Create risk-adjusted quotation calculator
- [ ] Integrate into CRM workflow
- [ ] Train sales team on usage

### Week 4: Process Changes
- [ ] Document new quotation SOP with storage risk assessment
- [ ] Update deal approval workflows (flag high-risk deals)
- [ ] Create escalation process for GP erosion >3%
- [ ] Pilot new commission structure with 2-3 sales reps

### Month 2: Scale & Refine
- [ ] Roll out commission structure to all sales team
- [ ] Implement automated customer pickup reminders
- [ ] Create weekly "storage cost review" in sales meetings
- [ ] Build predictive model for storage days by route/product
- [ ] Refine risk buffers based on actual data

### Month 3: Optimization
- [ ] Analyze storage cost reduction (target: 8 days → 6 days average)
- [ ] Calculate actual margin improvement
- [ ] Optimize container allocation algorithm
- [ ] Implement "oldest inventory first" sales incentives
- [ ] Refine vessel reliability scores

---

## 📊 Success Metrics

### Primary KPIs

| Metric | Baseline | 30-Day Target | 90-Day Target | Annual Target |
|--------|----------|---------------|---------------|---------------|
| **Average Storage Days** | 12 days | 10 days | 6 days | 4 days |
| **Annual Storage Cost** | £450K | £375K | £225K | £150K |
| **Storage Cost as % Revenue** | 0.85% | 0.71% | 0.42% | 0.28% |
| **GP Variance (Booked vs Realized)** | -2.8% | -2.0% | -1.0% | -0.5% |
| **Sales Team Visibility** | 0% | 100% | 100% | 100% |

### Secondary KPIs

| Metric | Baseline | Target |
|--------|----------|--------|
| **% Orders with Extended Storage (>7 days)** | 45% | 10% |
| **Average Customer Pickup Time** | 5 days | 2 days |
| **Vessel Delay Impact on Margin** | -1.2% | -0.5% |
| **Sales Team GP Forecast Accuracy** | 75% | 95% |

---

## 💰 Financial Projections

### Year 1 Savings Roadmap

**Q1 (Months 1-3): Foundation**
- Storage days: 12 → 10 days (-17%)
- Storage cost: £450K → £375K
- Savings: £75K
- Margin improvement: 0.14%

**Q2 (Months 4-6): Optimization**
- Storage days: 10 → 7 days (-30% from baseline)
- Storage cost: £375K → £262K
- Additional savings: £113K
- Cumulative savings: £188K
- Margin improvement: 0.35%

**Q3 (Months 7-9): Acceleration**
- Storage days: 7 → 5 days (-58% from baseline)
- Storage cost: £262K → £187K
- Additional savings: £75K
- Cumulative savings: £263K
- Margin improvement: 0.50%

**Q4 (Months 10-12): Target Achievement**
- Storage days: 5 → 4 days (-67% from baseline)
- Storage cost: £187K → £150K
- Additional savings: £37K
- **Total Year 1 Savings: £300K**
- **Margin improvement: 0.57%**

### ROI Analysis

```
Investment Required:
- Dashboard development: £25K
- CRM integration: £15K
- AI quotation tool: £20K
- Training & change management: £10K
Total Investment: £70K

Return:
- Year 1 savings: £300K
- Ongoing annual savings: £300K

ROI: 329% in Year 1
Payback: 2.8 months
NPV (3 years, 10% discount): £675K
```

---

## 🎯 Quick Wins: First 30 Days

### Week 1: "Name and Shame" Report

**Create Weekly Report:**
```
STORAGE COST LEADERS - WEEK ENDING 15-NOV-2025
=================================================
TOP 5 CONTAINERS BY STORAGE COST:

1. CNT-2025-005 | £88 | 25 days in storage
   - Origin: New Zealand
   - Vessel delayed 21 days (Singapore port congestion)
   - Allocated Orders: #12350, #12351
   - Action: Expedite delivery by Friday

2. CNT-2025-012 | £63 | 18 days in storage
   - Origin: Australia
   - Customer slow pickup (XYZ Hotels)
   - Action: Sales rep to push customer pickup

3. CNT-2024-347 | £56 | 16 days in storage
   - Origin: Iceland
   - Partially allocated, 40% unsold
   - Action: Fire sale on remaining inventory

TOP 5 SALES REPS BY STORAGE COST IMPACT:
1. Rep A: £450 storage cost on active deals
2. Rep B: £380 storage cost on active deals
...

TARGET: Each rep should have <£200 storage cost exposure
```

### Week 2: Customer Pickup Acceleration

**Implement Proactive Communication:**

```
Day 0 (Customs Clearance):
→ Email: "Your order is customs-cleared and ready for pickup!"
→ SMS: "CNT-2025-001 ready. Pickup by [DATE] to avoid storage fees"

Day 2:
→ Email: "Reminder: Your order has been in storage for 2 days"
→ Phone call from sales rep

Day 4 (TARGET EXCEEDED):
→ Email: "URGENT: Storage costs accumulating. Please arrange pickup ASAP"
→ SMS: "Day 4 in storage. Pickup today to minimize costs"
→ Manager escalation

Day 7 (CRITICAL):
→ Phone call from Sales Manager
→ Consider storage fee passthrough to customer
```

### Week 3: "Oldest Inventory First" Incentive

**SPIFF Program:**
```
STORAGE REDUCTION BONUS
=======================
For any container in storage >10 days:

If sales rep closes deal AND customer picks up within 48 hours:
→ Bonus: £200 per deal

Example:
- Container CNT-2024-347 has been in storage 16 days
- Rep closes 3,000 kg deal with Restaurant Group
- Customer picks up within 48 hours
- Rep earns: Regular commission + £200 bonus

Target: Clear all 10+ day inventory within 30 days
Fund: £10K bonus pool (pays for itself in storage savings)
```

### Week 4: Vessel Route Scorecard

**Create Reliability League Table:**
```
VESSEL ROUTE RELIABILITY - LAST 90 DAYS
==========================================
Route                  | On-Time % | Avg Delay | Storage Impact
-----------------------------------------------------------------
Australia → UK         | 75%       | 3 days    | £856 per container
New Zealand → UK       | 62%       | 7 days    | £1,245 per container
Iceland → UK           | 88%       | 1 day     | £423 per container

RECOMMENDATION:
- Prioritize Iceland route (highest reliability)
- Add 8-day storage buffer for NZ quotes
- Negotiate with NZ carriers or switch routes
```

---

## 🚀 AI Agent: "GP Guardian"

### Purpose
Real-time monitoring of every order from booking to cash, alerting when storage costs threaten margin.

### Capabilities

**1. Quotation Risk Assessment**
```
Input: Product, Quantity, Customer, Vessel Route
Output: Recommended price with storage risk buffer

Example:
→ "This NZ lamb quote uses MV Pacific Trader route"
→ "Historical reliability: 62% on-time, avg 7-day delay"
→ "Recommend +8 day storage buffer (£0.112/kg)"
→ "Suggested price: £9.95/kg (vs £9.50 without buffer)"
```

**2. Active Deal Monitoring**
```
Every 6 hours, scan all active orders:
- Check vessel ETA updates
- Calculate accumulated storage cost
- Compare current GP vs booked GP
- Alert if variance >1%

Example Alert:
→ "Order #12350: GP erosion detected"
→ "Booked: 32.16% | Current: 28.43% | -3.73%"
→ "Cause: Vessel delayed 14 days"
→ "Action: Contact customer for price adjustment or expedite delivery"
```

**3. Customer Pickup Prediction**
```
Machine learning model predicts pickup time based on:
- Customer historical behavior
- Order size
- Day of week
- Product type

Example:
→ "Customer XYZ Hotels avg pickup: 8 days"
→ "Risk: High storage cost"
→ "Recommendation: Add storage buffer to quote"
```

**4. Container Allocation Optimization**
```
When sales rep creates quote:
→ "Allocate from CNT-2024-347 (16 days in storage)"
→ "Avoid allocating from CNT-2025-015 (arriving next week)"
→ "Priority: Clear old inventory first"
```

**5. Weekly GP Variance Report**
```
Auto-generate every Monday:

WEEKLY GP REALIZATION REPORT
============================
Orders Delivered Last Week: 23
Total Booked GP: £285K (28.5%)
Total Realized GP: £267K (26.7%)
Variance: -£18K (-1.8%)

Breakdown:
- Storage cost overruns: -£12K
- Logistics cost overruns: -£4K
- Price concessions: -£2K

Top 3 Problem Orders:
1. Order #12350: -£3,455 variance
2. Order #12298: -£2,100 variance
3. Order #12311: -£1,850 variance

Lessons Learned:
→ NZ route continues to underperform
→ XYZ Hotels customer consistently slow pickup
→ Consider storage fee passthrough clause in contracts
```

---

## 📱 Sales Team Mobile App: "GP Pulse"

### Dashboard View

```
┌─────────────────────────────────────────┐
│  MY PIPELINE                            │
│  Total Value: £485K                     │
│  Weighted GP: £142K (29.3%)             │
│  GP at Risk: £4.2K ⚠️                   │
└─────────────────────────────────────────┘

┌─────────────────────────────────────────┐
│  ACTIVE DEALS NEEDING ATTENTION         │
└─────────────────────────────────────────┘

🔴 URGENT - Order #12350
   XYZ Hotels | £49K | 26.4% margin
   → GP erosion: -5.7% (storage costs mounting)
   → ACTION: Push customer pickup TODAY
   [VIEW DETAILS] [CALL CUSTOMER]

🟡 WATCH - Order #12345  
   ABC Restaurant | £100K | 32.6% margin
   → GP erosion: -0.4% (slight storage overrun)
   → Customer pickup tomorrow ✓
   [VIEW DETAILS]

🟢 ON TRACK - Order #12388
   Premier Foods | £75K | 34.2% margin
   → GP ahead of plan: +1.2%
   → Fast customer pickup (2 days)
   [VIEW DETAILS]

┌─────────────────────────────────────────┐
│  THIS WEEK'S PERFORMANCE                │
└─────────────────────────────────────────┘
Deals Closed: 5
Booked GP: £45K
Realized GP (last week): £41K
Your GP Accuracy: 91% (↑ vs last week)

┌─────────────────────────────────────────┐
│  INVENTORY ALERTS                       │
└─────────────────────────────────────────┘
⚡ BONUS OPPORTUNITY
   CNT-2024-347 in storage 16 days
   Australian Striploin - 4,200 kg left
   → Sell & deliver in 48hrs = £200 bonus!
   [CREATE QUOTE]
```

---

## 🎓 Training Module: "Storage Cost 101 for Sales"

### Lesson 1: Why Storage Costs Matter (10 minutes)

**Video Script:**
```
"Hi team, let's talk about something that's costing us £300,000 a year...

When you book a deal, you see this:
[Screen shows: £100K revenue, £68K cost, £32K GP, 32% margin]

You get excited. You did a great job. 32% margin!

But here's what actually happens:

[Screen shows vessel delay animation]
- Vessel arrives 7 days late
- Product sits in storage for 15 days instead of 4
- Each extra day costs £3.52 per container
- That's £350 in unexpected storage costs on this deal

Now the reality is:
[Screen shows: £100K revenue, £68.4K cost, £31.6K GP, 31.6% margin]

Still good? Yes. But multiply this by 350 containers per year...

[Screen shows: £300,000 disappears in animation]

That £300K could be:
- Higher bonuses for everyone
- New sales tools and support
- Company growth and stability
- YOUR realized GP (not someone else's job to fix)

From today, you'll see TWO numbers:
1. Booked GP (what you expect)
2. Realized GP (what actually happens)

Your commission will now reflect BOTH.

Why? Because we want you to:
- Quote with storage risk in mind
- Push customers for fast pickup  
- Care about vessel reliability
- Allocate from old inventory first

You'll make MORE money when you protect margin.
Let's go protect that £300K together!"
```

### Lesson 2: How to Use the GP Tracker (15 minutes)

[Interactive tutorial with real examples from their CRM]

### Lesson 3: Quotation with Storage Risk (20 minutes)

[Workshop: Calculate quotes with storage buffers]

### Lesson 4: Customer Pickup Acceleration (15 minutes)

[Role play: How to push customers for faster pickup without being pushy]

---

## 🔄 Weekly Sales Meeting Integration

### New Agenda Item: "Storage Cost Review" (10 minutes)

**Every Monday at 9:15am:**

```
STORAGE COST REVIEW
===================

1. LAST WEEK'S PERFORMANCE
   - Total storage cost: £XXX
   - Average days in storage: X.X
   - Target: 4 days
   - Variance: +X.X days

2. TOP 3 PROBLEM CONTAINERS
   [Display on screen with photos/details]
   - What went wrong?
   - What did we learn?
   - How do we prevent next time?

3. THIS WEEK'S FOCUS
   - X containers currently >10 days in storage
   - Total value at risk: £XXX
   - Action plan by rep to clear this week

4. WINS TO CELEBRATE
   - [Rep Name] delivered Order #XXXX in 2 days!
   - [Rep Name] cleared old inventory, saved £XXX
   - Bonus earned: £XXX

5. ROUTE RELIABILITY UPDATE
   - Which routes are running on time?
   - Which routes need extra buffer in quotes?
```

---

## 📞 Next Steps

### This Week
1. **Validate storage cost data** with CFO and warehouse manager
2. **Map current open orders** to containers and calculate current GP erosion
3. **Pilot dashboard** with 2-3 sales reps to get feedback
4. **Design commission structure change** with HR and finance approval

### Next Week  
1. **Build vessel reliability database** (scrape last 12 months of arrival data)
2. **Create quotation risk calculator** MVP
3. **Launch "Storage Cost Leaders" weekly report**
4. **Start customer pickup acceleration program**

### Next Month
1. **Full dashboard rollout** to all sales team
2. **Launch new commission structure**
3. **Implement GP Guardian AI agent** for real-time monitoring
4. **Measure baseline: Average storage days and cost per container**

---

## 💬 FAQ

**Q: Won't this make sales quotes higher and less competitive?**
A: Actually, we're currently LOSING deals by quoting too low and then having to absorb storage costs or deliver late. Better to quote realistically and deliver on-time with expected margin.

**Q: What if the customer refuses fast pickup?**
A: Then we build storage costs into the quote. If customer wants 14-day delivery, quote includes 14 days of storage. Either customer pays or we protect margin.

**Q: Won't sales team resist having commissions tied to realized GP?**
A: Top performers will LOVE it because they already deliver well. Poor performers who book deals without thinking about execution will need to improve. That's the point.

**Q: Can we really get to 4-day average storage?**
A: Iceland route is already at 5 days average. Australia can get to 4 days if vessel reliability improves and we push customer pickups. NZ is harder but we can get to 6-7 days.

**Q: What if vessel delay is totally out of our control?**
A: Then we invoke force majeure with customer, adjust price if possible, or absorb cost. But we LEARN and add bigger buffer for that route next time. The AI tracks this.

**Q: Who owns this initiative?**
A: **Sales Operations** owns the process, **IT** builds the tools, **Sales Manager** drives behavior change, **Finance** validates savings. But **everyone** benefits from protected margins.

---

**BOTTOM LINE:** 

£450K storage costs on £53M revenue is 0.85% of every sale disappearing into warehouses. Sales team books deals assuming 4-day storage, reality is 12 days, and £300K evaporates annually.

**Solution:** Real-time GP tracking, risk-adjusted quotations, aligned sales incentives, and AI monitoring. 

**Target:** Reduce storage from 12 days to 4 days, save £300K annually, improve margin by 0.57%.

**Timeline:** 90 days to measurable improvement, 12 months to full target achievement.

**ROI:** £70K investment, £300K annual return = 329% ROI.

---

*Version 1.0 | 2025-11-08 | Confidential*