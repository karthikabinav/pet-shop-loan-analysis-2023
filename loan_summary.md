# Pet Shop Loan Analysis 2023

**Loan Principal:** $45,000  
**Start:** March 2023 (3rd month)  
**Interest:** 5.12% per month, compounded monthly  
**Weekly Payment:** 12% of Weekly Profit  

## Weekly Financials Source
File: `/data/Pet Care 2023 Weekly Financials.csv`

Profit column per week extracted:
- Weeks 1-9 (Jan-Feb): pre-loan, no payments
- Week10-52 weekly profits used for payments

## Monthly Aggregated Profits & Payments (12%)
Based on end-date month assignment:

| Month | Weeks | Profit Sum | 12% Payment |
|-------|-------|------------|--------------|
| March | 10,11,12 | $20,051 | $2,406.12 |
| April | 13-17 | $32,681 | $3,921.72 |
| May | 18-21 | $25,004 | $3,000.48 |
| June | 22-25 | $26,817 | $3,218.04 |
| July | 26-30 | $33,672 | $4,040.64 |
| August | 31-34 | $25,869 | $3,104.28 |
| September | 35-38 | $26,658 | $3,198.96 |
| October | 39-43 | $33,503 | $4,020.36 |
| November | 44-47 | $26,927 | $3,231.24 |
| December | 48-52 | $33,933 | $4,071.96 |
| **Total** | 10-52 | $285,115 | **$34,213.80** |

## Loan Growth Without Payments
Compound factor for 10 months (Mar-Dec inclusive):
(1+0.0512)^10 = 1.64762
$45,000 * 1.64762 = **$74,142.30**

Minus total payments (simple):
$74,142.30 - $34,213.80 = **$39,928.50**

## Amortized Month-by-Month (interest first, then payment)
Starting balance $45,000 each month: balance = balance*1.0512 - payment

- Mar end: $44,897.88
- Apr end: $43,274.93
- May end: $42,490.13
- Jun end: $41,447.58
- Jul end: $39,529.06
- Aug end: $38,448.67
- Sep end: $37,218.28
- Oct end: $35,103.49
- Nov end: $33,669.55
- Dec end: **$31,321.47**

## Amortized Month-by-Month (payment first, then interest)
balance = (balance - payment)*1.0512

- Mar end: $44,774.69
- Apr end: $42,944.64
- May end: $41,989.30
- Jun end: $40,756.35
- Jul end: $38,595.55
- Aug end: $37,308.43
- Sep end: $35,855.87
- Oct end: $33,465.49
- Nov end: $31,782.24
- Dec end: **$29,129.05**

## Including Partial Week 9 (Feb27-Mar5)
If loan active Mar1, Week9 contributes 5/7 of its profit:
Week9 profit $6,340, 12% = $760.80, prorated 5/7 = $543.43
New March payment = $2,949.55
Final balance (interest-first): **$30,469.73**

## Including Full Week 9
March payment = $2,406.12 + $760.80 = $3,166.92
Final balance (interest-first): **$30,129.03**

## Answer Summary
Depending on assumption:
- **Simple subtraction:** ~$39,929 still owed
- **Realistic amortization (interest then payment):** **$31,321** owed at Dec 31 2023
- **Payment-first model:** **$29,129** owed
- **With prorated Week9:** **$30,470** owed

Recommended figure using standard loan practice (interest accrues, payment at month-end): **$31,321.47** by end of 2023.

If you continue same payment rate (~$34k paid in 10 months), you'd need roughly another year to clear the loan, assuming similar profits and no additional interest changes.
