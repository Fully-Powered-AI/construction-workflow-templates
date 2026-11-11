# Pay application line check: an invented example

*Illustrative example with invented data.* An invented tenant fit-out, "Project Alpha", with an invented contractor and owner. Every figure below is made up for this page, and no real company, person or project is meant. The project accountant supplies five documents and three settings, and receives one page.

## What the project accountant supplies

**Settings.** Evidence tolerance: 0.50 percentage points. Retainage rate: 5% of total completed and stored. Status words that count as approved: Approved.

**Pay application 4** (Project Alpha, Contractor A, dated 2 November 2026, period to 31 October 2026). Original contract sum 500000. Retainage 16300. Total earned less retainage 309700. Less previous certificates for payment 215650. Current payment due 94050.

```
Line,Description,Scheduled value,Previous billed,This period,Stored materials,Total completed and stored,Percent complete,Balance to finish
01,General conditions,60000,24000,6000,0,30000,50.00,30000
02,Concrete,162000,120000,30000,0,150000,92.59,12000
03,Framing,120000,48000,24000,12000,84000,70.00,36000
04,Electrical,90000,27000,18000,0,46000,51.11,44000
05,Finishes,89000,8000,8000,0,16000,17.98,73000
Totals,,521000,227000,86000,12000,326000,,195000
```

**Schedule of values** (Project Alpha, the project's starting version).

```
Line,Description,Scheduled value
01,General conditions,60000
02,Concrete,150000
03,Framing,120000
04,Electrical,90000
05,Finishes,80000
```

**Change log** (Project Alpha, as of 31 October 2026).

```
Change,Description,Amount,Status,Approval date,Line
CO-1,Slab openings added,12000,Approved,2026-09-14,02
CO-2,Additional outlets,6000,Approved,2026-10-20,04
CO-3,Upgraded floor finish,9000,Pending,,05
```

**Prior certificate** (Project Alpha, number 3, dated 2 October 2026, total earned less retainage 213750, the cumulative amount certified to date).

```
Line,Certified to date
01,24000
02,120000
03,48000
04,27000
05,6000
```

**Progress evidence** (Project Alpha).

```
Line,Source,Date,Percent complete,Stored materials supported
01,Superintendent log,2026-10-30,50.00,
02,Inspection report,2026-10-28,92.00,
03,Superintendent log and delivery receipts,2026-10-30,60.00,9500
04,Electrical inspection report,2026-10-29,40.00,
```

## What comes out

```
PAY APPLICATION LINE CHECK: Project Alpha, application 4, period to 31 October 2026

Prepared for: the project accountant. Basis: application 4 dated 2 November 2026; schedule of values (starting version); change log as of 31 October 2026; prior certificate 3 dated 2 October 2026; progress evidence from the superintendent log (30 October), the inspection report (28 October), the electrical inspection report (29 October) and delivery receipts.
Settings used: evidence tolerance 0.50 points; retainage rate 5% of total completed and stored; approved status word: Approved.

Totals: 5 lines checked. 11 differences: 8 on lines 02 to 05, 3 on page figures. Lines with no difference: 01.

Checks that agree: original contract sum 500,000 equals the schedule of values. Scheduled values on lines 01, 02 and 03 equal the schedule of values plus approved changes (line 02 includes CO-1, 12,000). Within each line, percent complete and balance to finish follow from the total shown. Totals for scheduled value, previous billed, this period, stored materials, total and balance equal the sums of their lines. Previous billed on lines 01 to 04 equals the prior certificate. Progress evidence on lines 01 and 03 agrees with the claim within tolerance. Retainage 16,300 equals 5% of 326,000. Total earned less retainage 309,700 equals 326,000 less 16,300. Current payment due 94,050 equals 309,700 less 215,650.

A. Arithmetic on the page
1. Line 04, total completed and stored: shown 46,000; previous 27,000 + this period 18,000 + stored 0 = 45,000; difference 1,000. Percent complete 51.11 and balance 44,000 follow from the 46,000 shown. Ask: contractor's billing contact.
2. Totals row, total completed and stored: shown 326,000; the parts give previous 227,000 + this period 86,000 + stored 12,000 = 325,000; difference 1,000. Follows from item 1.

B. Previous billing against the prior certificate
3. Line 05, previous billed: application 8,000; prior certificate 6,000; difference 2,000. The previous billed total of 227,000 is 2,000 above the certificate's total of 225,000 for the same reason. Ask: contractor's billing contact.

C. Changes against the schedule of values
4. CO-2, line 04, Approved, 6,000: not on the application. Scheduled value shown 90,000; schedule of values 90,000 plus CO-2 6,000 = 96,000. Ask: project manager.
5. CO-3, line 05, status Pending, 9,000: included in the application. Scheduled value shown 89,000; schedule of values 80,000, with no approved change on this line, gives an expected 80,000. Ask: project manager.
6. Scheduled value total: shown 521,000; schedule of values 500,000 plus approved changes 18,000 = 518,000; difference 3,000, being the 9,000 in item 5 less the 6,000 in item 4. Follows from items 4 and 5.

D. Progress evidence
7. Line 02: claimed 92.59% (150,000 over 162,000); evidence 92.00% (inspection report, 28 October); 0.59 points above. Evidence implies 149,040; claimed 150,000; amount in question 960. Ask: superintendent.
8. Line 04: claimed 51.11% (46,000 less stored 0, over 90,000); evidence 40.00% (electrical inspection report, 29 October); 11.11 points above. Evidence implies 36,000; claimed 46,000; amount in question 10,000. Ask: superintendent.
9. Line 05: no evidence supplied. Billed to date 16,000. Ask: superintendent.

E. Stored materials
10. Line 03: billed 12,000; supported 9,500 (superintendent log and delivery receipts, 30 October); unsupported 2,500. Ask: superintendent.

F. Retainage and amount due
11. Less previous certificates for payment: application 215,650; prior certificate 213,750; difference 1,900. Follows from item 3.

Amount due as stated: 94,050. The page's own arithmetic from retainage to amount due agrees. This comparison does not restate it.

Not checked: the 5% retainage rate was used as supplied and not checked against the contract. Nothing else left unchecked.

The project accountant verifies each figure against the documents. The authorized certifier decides payment and completion. This comparison certifies no completion percentage, interprets no contract term and changes no record.
```
