# Duplicate Payment Detection – Accounts Payable Control

## Overview
This Excel-based workbook is designed to detect and report potential duplicate vendor payments within an Accounts Payable workflow.

The file uses formula-driven logic to automatically flag duplicate invoices based on:
- Vendor Name
- Invoice Number
- Invoice Amount

This helps prevent overpayments and strengthens internal AP controls.

---

## Features

- Automated duplicate detection using COUNTIFS
- Invoice status tracking (Paid / Unpaid)
- Separate duplicate-only review sheet
- Summary report showing:
  - Total duplicate invoices
  - Total duplicate exposure amount

---

## How Duplicate Detection Works

The workbook uses the following Excel formula:

=IF(COUNTIFS($A:$A,A2,$B:$B,B2,$D:$D,D2)>1,"DUPLICATE","OK")

If the combination of Vendor + Invoice Number + Amount appears more than once, the invoice is flagged as DUPLICATE.

---

## Sheets Included

1. Invoice_Data – Main data entry sheet
2. Duplicate_Only_View – Filtered duplicate invoices
3. Summary_Report – Dashboard showing duplicate counts and financial impact

---

## Purpose

This project demonstrates:
- Strong knowledge of Accounts Payable processes
- Internal control awareness
- Excel automation skills
- Reconciliation and exception handling

---

## Tools Used

- Microsoft Excel
- COUNTIFS
- IF logic
- Conditional Formatting
- Basic Reporting Controls

---

## Author

Vipin
Accounts Payable Professional
