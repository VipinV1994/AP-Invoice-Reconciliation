# Vendor Aging Tracker – Accounts Payable

## Overview
This Excel-based Vendor Aging Tracker monitors outstanding invoices and categorizes them into aging buckets to support cash flow management and vendor risk analysis.

---

## Features

- Paid vs Unpaid tracking
- Automatic days outstanding calculation
- Aging bucket classification:
  - 0–30 Days
  - 31–60 Days
  - 61–90 Days
  - 90+ Days
- Vendor-wise aging summary using Pivot Table

---

## Key Formulas Used

Status:
=IF(ISBLANK(F2),"Unpaid","Paid")

Days Outstanding:
=IF(G2="Paid",0,TODAY()-D2)

Aging Bucket:
=IF(G2="Paid","Paid",
IF(H2<=30,"0-30 Days",
IF(H2<=60,"31-60 Days",
IF(H2<=90,"61-90 Days",
"90+ Days"))))

---

## Purpose

This project demonstrates:
- Strong Accounts Payable knowledge
- Aging analysis skills
- Excel automation and reporting
- Cash flow and vendor risk monitoring

---

## Author
Vipin
Accounts Payable Professional
