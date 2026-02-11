# Corporate Card Reconciliation Control
GitHub Project Name: Corporate-Card-Reconciliation-Control
Purpose: Audit-ready corporate card reconciliation workbook with pivot dashboard, showing policy compliance, duplicate detection, aging, and risk levels.

---

## Sheet 1: Card_Transactions
Headers (A-P):
A  Cardholder Name
B  Department
C  Transaction Date
D  Statement Month
E  Vendor Name
F  Expense Category
G  Business Purpose
H  Transaction Amount
I  Receipt Received (Yes/No)
J  Expense Report Submitted (Yes/No)
K  Policy Limit
L  Over Limit Flag
M  Missing Receipt Flag
N  Duplicate Flag
O  Days Outstanding
P  Risk Level

Formulas:
L2 (Over Limit Flag): =IF(H2>K2,"Over Limit","OK")
M2 (Missing Receipt Flag): =IF(I2="No","Missing Receipt","OK")
N2 (Duplicate Detection): =IF(COUNTIFS($C:$C,C2,$E:$E,E2,$H:$H,H2)>1,"Duplicate","OK")
O2 (Days Outstanding): =IF(J2="No",TODAY()-C2,0)
P2 (Risk Level): 
=IF(L2="Over Limit","High",
IF(M2="Missing Receipt","High",
IF(N2="Duplicate","High",
IF(O2>30,"Medium","Low"))))

Optional Enhancements:
- Auto policy limit lookup by category (VLOOKUP/XLOOKUP)
- Escalation flag after 45 days
- Department risk scoring
- Trend analysis by month

---

## Sheet 2: Compliance_Dashboard
KPI Metrics:
Total Transactions =COUNTA(Card_Transactions!A:A)-1
Over Limit Count   =COUNTIF(Card_Transactions!L:L,"Over Limit")
Missing Receipts   =COUNTIF(Card_Transactions!M:M,"Missing Receipt")
Duplicates         =COUNTIF(Card_Transactions!N:N,"Duplicate")
High Risk          =COUNTIF(Card_Transactions!P:P,"High")

Pivot Table Setup:
- Rows → Cardholder Name
- Columns → Risk Level
- Values → Cardholder Name (set to Count)

Conditional Formatting:
- High → Red
- Medium → Orange
- Low → Green

Optional: Add Slicer for Risk Level

---

## GitHub Instructions

