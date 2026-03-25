# 📊 Customer Support Ticket Analysis — README

> A complete beginner-friendly guide to understanding this data analysis project

---

## 📁 What Is This Project?

This project analyzes **customer support tickets** from a company to find patterns, problems, and areas of improvement in their support system.

The data comes from a file called `customer_support_tickets.csv` and contains **8,469 support tickets** raised by customers between **2020 and 2021**.

The goal is to answer business questions like:
- Which products have the most problems?
- How fast does support respond?
- Are issues getting resolved?
- Which customers complain the most?

---

## 🛠️ Tools & Libraries Used

| Library | What it does |
|---|---|
| `pandas` | Loads and cleans data (like Excel but in Python) |
| `numpy` | Helps with number calculations |
| `matplotlib` | Creates charts and graphs |
| `seaborn` | Makes nicer-looking charts |

---

## 📂 Dataset Overview

- **File used:** `customer_support_tickets.csv`
- **Total rows (tickets):** 8,469
- **Columns include:** customer age, gender, product purchased, ticket type, ticket status, ticket priority, ticket channel, satisfaction rating, dates, and resolution info

---

## 🧹 Step 1 — Data Cleaning

Before analysis, the raw data was cleaned up. Here's what was done:

### Column Names Fixed
All column names were made **lowercase** and **spaces replaced with underscores** (e.g., `Date Of Purchase` → `date_of_purchase`) so they're easier to work with in code.

### Date Columns Converted
These columns were stored as plain text (strings) and were converted to proper **date/time format**:
- `date_of_purchase`
- `first_response_time`
- `time_to_resolution`

This allows calculating how many hours it took to respond or resolve a ticket.

### Missing Values Handled

| Column | Missing Count | What Was Done |
|---|---|---|
| `resolution` | ~5,700 | Filled with `0` (meaning "not resolved yet") |
| `first_response_time` | Some | Kept as is for calculations |
| `time_to_resolution` | Some | Kept as is for calculations |
| `customer_satisfaction_rating` | Some | Kept as is |

> 💡 The 5,700 missing resolutions mean those tickets were **never resolved** — a big red flag for the company.

### Ticket Status Simplified
`"Pending Customer Response"` was renamed to just `"Pending"` to keep it consistent.

---

## 📊 Step 2 — Exploratory Data Analysis (EDA)

Basic distributions were plotted for:
- **Gender** → Males raise more tickets than females
- **Ticket Type** → Refund requests and technical issues are most common
- **Ticket Status** → Pending tickets are the majority
- **Ticket Channel** → Email is used the most

---

## ❓ Step 3 — Business Questions Answered

### Q1. Which products generate the highest number of support tickets?
- **Canon EOS** generates the most support tickets among all products.
- This suggests the Canon EOS may have more defects or usability issues compared to other products. The company should investigate it.

---

### Q2. What are the top 5 most common customer issues?
The most frequently raised complaint types are:
1. **Refund Request** (most common)
2. **Software Bug**
3. Followed by others like billing, shipping, and product issues

This shows customers face a lot of refund-related and software problems.

---

### Q3. What percentage of tickets are technical vs non-technical?
- **~79% are Non-Technical** (refunds, billing, cancellations, inquiries)
- **~21% are Technical** (product/software bugs)

Most issues are business process problems, not technical ones.

---

### Q4. Which ticket priorities are most frequent?
The analysis looked at how many tickets were marked as:
- Critical
- High
- Medium
- Low

All four priorities have similar counts — support issues are spread evenly across urgency levels.

---

### Q5. What proportion of tickets remain unresolved?
- **67.30% of tickets are UNRESOLVED** (only "Closed" tickets count as resolved)
- Only **32.70%** are resolved

This is a **major problem** — more than 2 out of 3 tickets haven't been closed. This creates a backlog and hurts customer trust.

---

### Q6. What is the average first response time?
- **Response time** = Time from purchase date to when support first replied
- The average first response time was calculated in **hours** (converting from seconds using `/3600`)

---

### Q7. What is the average time to resolution?
- **Resolution time** = Time from purchase date to when the ticket was closed
- Also calculated in **hours**

---

### Q8. Which ticket types take the longest to resolve?
- **Refund Request tickets** take the longest time to resolve on average
- This means refund processes are slower or more complex than other ticket types

---

### Q9. What percentage of tickets are resolved within SLA (24 hours)?
- **0% of tickets** were resolved within 24 hours
- This means the company is completely **failing their SLA (Service Level Agreement)**
- Every single ticket took more than 24 hours to resolve — a critical efficiency failure

---

### Q10. Which channel receives the most tickets?
Channels analyzed: **Email, Phone, Chat, Social Media**

- **Email** receives the most tickets
- **Phone** is the second most used
- Chat and Social Media are less used

---

### Q11. Which channel has the fastest response time?
- **Social Media** has the fastest first response time
- This means when customers complain on social media, support replies the quickest

---

### Q12. Which channel has the fastest resolution time?
- **Social Media** also has the fastest resolution time
- This suggests social media tickets are handled more urgently (probably due to public visibility)
- The company should try to bring the same speed to other channels like Email and Phone

---

### Q13. Which channel results in highest customer satisfaction?
- **All channels have the same average satisfaction rating of 3/5**
- No channel is performing better or worse than others
- Since Email handles the most tickets, improving Email support would have the biggest overall impact

---

### Q14. Which age group raises the most complaints?
Customers were grouped as:
- Kid (under 12)
- Teenager (12–18)
- Adult (19–38)
- **Middle Aged (39–58)** ← raises the MOST tickets
- Senior Citizen (59+)

Middle-aged customers are the most active in raising support complaints.

---

### Q15. Do male/female/other customers show different complaint patterns?
- Males and females show **very similar complaint patterns** across all ticket types
- Females raise slightly more **refund requests**
- Males raise slightly more **cancellation requests**
- "Other" gender has fewer tickets overall
- Support resources should be **equally distributed** across genders

---

### Q16. Which products have the most critical issues?
- **Canon EOS** again tops the list — it has the most tickets marked as "Critical"
- This makes it the highest-priority product for the quality/engineering team to investigate

---

### Q17. Which products take the longest to resolve issues?
- **Fitbit Versa Smartwatch** has the longest average resolution time — approximately **22,417 hours** (~934 days!)
- This is extremely high and suggests something is wrong with how Fitbit-related issues are handled

---

### Q18. Which products receive the lowest satisfaction ratings?
- **All products have the same average satisfaction rating of 3/5**
- No single product stands out as worse — dissatisfaction is uniform across all products

---

### Q19. How does ticket volume change over months/years?
- Ticket volume was tracked by **year and month**
- The data shows how busy the support team was at different times

---

### Q20. Are complaints increasing or decreasing?
- **Ticket volume is clearly decreasing year over year**
- This is a positive sign — fewer customers are raising complaints over time

---

### Q21. Are response times improving over time?
- **Yes — average response time is decreasing year over year**
- The company is getting faster at giving first responses
- This is a positive improvement trend

---

### Q22. Are resolution times improving?
- **Yes — resolution time is also decreasing over time**
- Support is resolving issues faster as years go by

---

### Q23. Does faster response time lead to higher satisfaction?
- A scatter plot was created comparing **response time vs customer satisfaction rating**
- This was used to check if customers who got faster replies gave higher ratings

---

## 🔑 Final Summary — Key Takeaways

| Finding | Value |
|---|---|
| Total Tickets | 8,469 |
| Time Period | 2020–2021 |
| Unresolved Tickets | **67.3%** |
| SLA Compliance (24 hrs) | **0%** |
| Top Problem Product | **Canon EOS** |
| Longest Resolution Time | **Fitbit Versa (~22,417 hrs)** |
| #1 Complaint Type | **Refund Request** |
| Non-Technical Tickets | **~79%** |
| Avg Satisfaction Rating | **3/5 (all channels & products)** |
| Most Active Age Group | **Middle Aged (39–58)** |
| Most Used Channel | **Email** |
| Fastest Channel | **Social Media** |
| Ticket Volume Trend | **Decreasing ✅** |
| Response Time Trend | **Improving ✅** |
| Resolution Time Trend | **Improving ✅** |

---

## 💡 Business Recommendations

Based on this analysis, here are the key actions the company should take:

1. **Fix the backlog** — 67% unresolved tickets is critical. Hire more agents or automate common responses.
2. **Improve SLA compliance** — Aim to resolve at least basic tickets within 24 hours.
3. **Investigate Canon EOS** — It has the most tickets AND the most critical issues. Product quality needs review.
4. **Fix Fitbit Versa resolution delays** — ~22,000 hour resolution time is unacceptable.
5. **Streamline the refund process** — It's the #1 complaint AND takes the longest to resolve.
6. **Replicate Social Media speed across channels** — Social media handles tickets fastest; apply those practices to Email and Phone too.
7. **Focus on middle-aged customers** — They raise the most tickets; understand their pain points better.

---

## 📌 How to Run This Notebook

1. Make sure you have Python installed
2. Install required libraries:
   ```bash
   pip install pandas numpy matplotlib seaborn
   ```
3. Place the `customer_support_tickets.csv` file in a `../data/` folder (one level above the notebook)
4. Open the `.ipynb` file in **Jupyter Notebook** or **JupyterLab**
5. Run all cells from top to bottom

---

*README generated from `customer_support_analysis.ipynb`*