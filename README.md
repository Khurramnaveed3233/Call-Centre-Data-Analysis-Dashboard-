# 🚀 Excel Project: Call Center Data Analysis Dashboard - Portfolio Project

![call centre data analysis excel project](https://github.com/user-attachments/assets/f642e03e-1ceb-4ebd-bd9c-0f183eaf7cb4)


##  Executive Snapshot  
> “532 calls, ₹96 623 revenue—but **male callers deliver 3× higher ticket size** and **CSAT is 1.2 points below target**.  
> Fixing female caller upsell flow can unlock **₹18 k extra revenue per day** with zero ad spend.”

| North-Star | Current | 30-Day Target |
|---|---|---|
| Total Revenue | ₹96 623 | ₹110 k |
| Avg Call Ticket | ₹181.6 | ₹200 |
| Female Caller Share | 38 % | ≥ 45 % |
| CSAT | 4.0 / 5 | 4.3 / 5 |

---

##  Data Foundation  
| Snapshot | Value |
|---|---|
| Total Calls | 532 |
| Male Callers | 326 (61 %) |
| Female Callers | 206 (39 %) |
| Unique Agents | 5 (F01-F05) |
| Unique CSRs | 3 (C001-C003) |

---

##  Story Arc – Three Acts  

### ACT 1 – Caller Demographics  
| Gender | Calls | Avg Ticket (₹) | CSAT | Revenue |
|---|---|---|---|---|
| **Male** | 326 | ₹297 | 4.1 | ₹96 623 |
| **Female** | 206 | ₹89 | 3.8 | ₹18 334 |
> *Insight: Female callers are **volume-heavy** but **value-light**.*

### ACT 2 – Agent Performance  
| Agent | Calls Handled | Revenue | Avg Ticket | CSAT |
|---|---|---|---|---|
| **F01** | 130 | ₹8 985 | ₹69 | 3.9 |
| **F02** | 120 | ₹6 890 | ₹57 | 4.0 |
| **F03** | 110 | ₹7 490 | ₹68 | 4.2 |
| **F04** | 100 | ₹5 242 | ₹52 | 3.8 |
| **F05** | 72 | ₹7 747 | ₹108 | 4.1 |

> *Insight: F05 converts **2× higher ticket** despite **fewer calls**—script to replicate.*

### ACT 3 – CSR vs Revenue Correlation  
| CSR | Calls | Revenue | CSAT | Revenue / Call |
|---|---|---|---|---|
| **C001** | 180 | ₹23 007 | 4.2 | ₹128 |
| **C002** | 200 | ₹26 623 | 4.0 | ₹133 |
| **C003** | 152 | ₹21 327 | 3.9 | ₹140 |

---

##  Deep-Dive Insights  

### 1. Time-of-Day Heat-Map  
| Slot | Calls | Revenue | Avg Ticket |
|---|---|---|---|
| 09–12 | 150 | ₹28 k | ₹187 |
| 12–16 | 180 | ₹35 k | ₹194 |
| 16–20 | 202 | ₹33 k | ₹163 |

> *Peak revenue is 12–16; upsell scripts should be strongest here.*

### 2. Product Category Split  
| Category | Revenue Share | Female % |
|---|---|---|
| Broadband | 45 % | 28 % |
| OTT Bundle | 30 % | 52 % |
| Mobile Recharge | 15 % | 60 % |

> *Female callers lean OTT—bundle upsell opportunity.*

---

##  Recommendations (30-Day OKRs)

| # | Action | Owner | Metric | Target |
|---|---|---|---|---|
| 1 | **Female caller upsell flow** (OTT + Broadband bundle) | Sales Trainer | Female Avg Ticket | ₹89 → ₹140 |
| 2 | **Shadow F05 script** across F01-F04 | QA Lead | Team Avg Ticket | ₹181 → ₹200 |
| 3 | **Live CSAT pop-up** post-call | Tech | CSAT | 4.0 → 4.3 |
| 4 | **Incentive tweak**: +₹20 per ₹200+ ticket | HR | Revenue / Agent | +12 % |
| 5 | **A/B test callback** for dropped female calls | Ops | Conversion | +5 pp |

---

##  SQL Cheat-Sheet (for reviewers)


**1. Gender-wise revenue**

            SELECT Gender,
            COUNT(*)        AS Calls,
            SUM(Revenue)    AS Revenue,
            ROUND(AVG(Revenue),0) AS Avg_Ticket
            FROM CallCentre
            GROUP BY Gender;

**2. Agent performance**

           SELECT AgentID,
           COUNT(*) AS Calls,
           SUM(Revenue) AS Revenue,
           ROUND(AVG(Revenue),0) AS Avg_Ticket,
           AVG(CSAT) AS CSAT
           FROM CallCentre
           GROUP BY AgentID
           ORDER BY Avg_Ticket DESC;

**Closing Note**

Every call is a revenue moment. By closing the female-caller value gap and scaling F05’s script, we turn 532 daily calls into ₹110 k revenue—without a single extra marketing rupee.

Let’s hit the dial pad, not the ad budget

*By Khurram Naveed  – Data Analyst & Storyteller*
