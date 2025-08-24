# Branch Strategy Insights Report: Custom DAX Measures

## Overview: Why These Measures Were Created

In support of the **Branch Strategy Insights Analysis**, it was necessary to create a targeted set of DAX measures to evaluate core KPIs across multiple dimensions of performance. These measures were designed to uncover patterns in **operational efficiency**, **cost to serve**, **loan and deposit dynamics**, **revenue generation**, and **customer engagement behaviors**; particularly across segments, products, and time. Together, they provide the analytical backbone needed to assess branch-level effectiveness, highlight opportunities for strategic enablement, and align insights with macroeconomic conditions and evolving consumer behaviors.

---

## Custom DAX Measures

### 1. **Loan Penetration % (Scaled)**

```DAX
Loan_Penetration_Percent_Scaled = DIVIDE(SUM(Fact_BranchPerformance[Total_Loan_Volume]), SUM(Fact_BranchPerformance[Total_Customers])) * 100
```

**Purpose:**  
Calculates the percentage of customers with loans, scaled for benchmarking across branches.

**Helps answer:**  
How effective is each branch at penetrating its customer base with loan products?

---

### 2. **Estimated Interest Revenue (Scaled)**

```DAX
Estimated_Interest_Revenue_Scaled = SUM(Fact_BranchPerformance[Estimated_Interest_Revenue]) / 1000
```

**Purpose:**  
Scales raw interest revenue to a more interpretable unit (e.g., in thousands or millions).

**Helps answer:**  
Which branches or segments generate the most interest revenue from lending activity?

---

### 3. **Total Deposits (Scaled)**

```DAX
Total_Deposits_Scaled = SUM(Fact_BranchPerformance[Total_Deposits]) / 1000
```

**Purpose:**  
Scales total deposits to make comparisons easier across branches or customer segments.

**Helps answer:**  
Which branches are most effective at attracting and retaining deposit balances?

---

### 4. **Total Operational Costs (Scaled)**

```DAX
Total_Operational_Costs_Scaled = SUM(Fact_BranchPerformance[Operational_Costs]) / 1000
```

**Purpose:**  
Normalizes cost data for efficiency comparisons.

**Helps answer:**  
Where are operational costs disproportionately high, and how might this impact profitability?

---

### 5. **Total Loan Volume (Scaled)**

```DAX
Total_Loan_Volume_Scaled = SUM(Fact_BranchPerformance[Total_Loan_Volume]) / 1000
```

**Purpose:**  
Scales total loan volume to allow clearer comparison of lending volume.

**Helps answer:**  
Which branches are lending at higher volumes and could be over- or under-leveraged?

---

### 6. **Revenue per Customer (Scaled)**

```DAX
Revenue_per_Customer_Scaled = DIVIDE(SUM(Fact_BranchPerformance[Estimated_Total_Revenue]), SUM(Fact_BranchPerformance[Total_Customers])) / 1000
```

**Purpose:**  
Calculates revenue efficiency on a per-customer basis, scaled.

**Helps answer:**  
Which branches or segments generate the most revenue per customer served?

---

### 7. **Estimated Total Revenue (Scaled)**

```DAX
Estimated_Total_Revenue_Scaled = SUM(Fact_BranchPerformance[Estimated_Total_Revenue]) / 1000
```

**Purpose:**  
Scales total estimated revenue to simplify visual comparisons and ratio building.

**Helps answer:**  
Which regions or branches are responsible for generating the bulk of the bank's revenue?

---

### 8. **Average Satisfaction Score**

```DAX
Average_Satisfaction_Score = AVERAGE(Fact_BranchPerformance[Branch_Satisfaction_Score])
```

**Purpose:**  
Calculates average customer satisfaction per branch or segment.

**Helps answer:**  
Where is customer satisfaction strongest, and does it correlate with profitability or growth?

---

### 9. **Estimated Profit**

```DAX
Estimated_Profit = SUM(Fact_BranchPerformance[Estimated_Total_Revenue]) - SUM(Fact_BranchPerformance[Operational_Costs])
```

**Purpose:**  
Estimates profitability after subtracting operational expenses.

**Helps answer:**  
Which branches are most profitable in real terms, and which are underperforming?

---

### 10. **Average Loan Amount (Scaled)**

```DAX
Scaled_Avg_Loan_Amount = DIVIDE(SUM(Fact_BranchPerformance[Total_Loan_Volume]), SUM(Fact_BranchPerformance[Total_Customers])) / 1000
```

**Purpose:**  
Tracks the average size of loans issued, scaled down for comparison.

**Helps answer:**  
Are certain segments or branches issuing smaller or larger average loans?

---

### 11. **Operational Cost per Customer**

```DAX
Operational_Cost_per_Customer = DIVIDE(SUM(Fact_BranchPerformance[Operational_Costs]), SUM(Fact_BranchPerformance[Total_Customers]))
```

**Purpose:**  
Calculates how much it costs to serve one customer.

**Helps answer:**  
Which branches or segments are least efficient in delivering services?

---

### 12. **Loan Revenue Efficiency Ratio**

```DAX
Loan_Revenue_Efficiency = DIVIDE(SUM(Fact_BranchPerformance[Estimated_Interest_Revenue]), SUM(Fact_BranchPerformance[Total_Loan_Volume]))
```

**Purpose:**  
Shows how much revenue is generated per dollar of loans issued.

**Helps answer:**  
Are branches issuing loans that are translating into high interest returns?

---

### 13. **Percent Digital Usage**

```DAX
Percent_Digital_Usage = AVERAGE(Fact_BranchPerformance[Percent_Digital_Usage])
```

**Purpose:**  
Averages digital usage to assess digital channel adoption.

**Helps answer:**  
How digitally engaged are customers at each branch, and what does that imply for staffing or services?

---

✅ *All DAX measures were created in alignment with Power BI best practices and tailored to the specific structure of the `Fact_BranchPerformance` table and supporting dimension tables (`Dim_Branch_Region`, `Dim_Product_Service`, and `Dim_Customer_Segment`).*
