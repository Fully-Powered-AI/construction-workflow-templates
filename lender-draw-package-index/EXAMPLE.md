# Lender draw package index: an invented example

*Illustrative example with invented data.* An invented apartment project, "Project Delta", with an invented lender, contractor and suppliers. Every figure below is made up for this page, and no real company, person or project is meant. The project accountant supplies five documents and a few settings, and receives one page.

## What the project accountant supplies

**Settings.** Project: Project Delta. Draw 5, period 1 October to 31 October 2026. Draw amount entered on the lender's form: 487,500.00. Ledger statuses that count as posted: Posted. Role asked about ledger differences: project accountant. Lender: Lender X, checklist version of 1 September 2026. Accounting export as of 2 November 2026; attachments list as of 2 November 2026.

**The lender's checklist** (Lender X, version of 1 September 2026).

```
Item,Section,Document required,Scope,Required,Ask
1,Cost,Invoice for each cost in the draw,Invoice,Yes,Accounts payable
2,Cost,Lien waiver for each payee,Payee,Yes,Project manager
3,Progress,Contractor's pay application,Draw,Yes,Project accountant
4,Progress,Inspection report for the period,Draw,Yes,Project manager
5,Title,Title date-down report,Draw,Yes,Project finance lead
6,Insurance,Insurance certificate update,Draw,No,Project finance lead
```

**The draw schedule.**

```
Invoice,Payee,Budget line,Amount
A-1101,Contractor A,Hard costs,412500.00
S-2207,Supplier B,Site work,38250.00
D-0415,Design Firm C,Soft costs,12400.00
P-3390,Supplier D,Soft costs,6850.00
E-0188,Supplier E,Site work,9200.00
F-0770,Insurance Broker F,Soft costs,4300.00
```

**The accounting export** (as of 2 November 2026).

```
Invoice,Payee,Posting date,Amount,Budget line,Status
A-1101,Contractor A,2026-10-28,412500.00,Hard costs,Posted
S-2207,Supplier B,2026-10-15,38250.00,Site work,Posted
D-0415,Design Firm C,2026-10-09,12400.00,Hard costs,Posted
P-3390,Supplier D,2026-10-20,6580.00,Soft costs,Posted
F-0770,Insurance Broker F,2026-10-30,4300.00,Soft costs,Entered
S-2231,Supplier B,2026-10-22,15000.00,Site work,Posted
```

**The attachments listed** (as of 2 November 2026).

```
Item,Payee,Invoice,File name,Document date
1,Contractor A,A-1101,a-1101.pdf,2026-10-27
1,Supplier B,S-2207,s-2207.pdf,2026-10-14
1,Design Firm C,D-0415,d-0415.pdf,2026-10-08
1,Supplier D,P-3390,p-3390.pdf,2026-10-19
1,Insurance Broker F,F-0770,f-0770.pdf,2026-10-29
2,Contractor A,,waiver-contractor-a.pdf,2026-10-30
2,Supplier B,,waiver-supplier-b.pdf,2026-10-30
2,Design Firm C,,waiver-design-firm-c.pdf,2026-10-30
2,Supplier D,,waiver-supplier-d.pdf,2026-10-30
3,,,pay-app-5.pdf,2026-11-02
5,,,title-date-down-oct.pdf,2026-10-30
8,,,site-photos.zip,2026-10-30
```

## What comes out

```
LENDER DRAW PACKAGE INDEX: Project Delta, draw 5, period 1 October 2026 to 31 October 2026

Prepared for: the project finance lead. Basis: Lender X checklist of 1 September 2026; draw schedule of 6 invoices; accounting export as of 2 November 2026; attachments listed as of 2 November 2026.
Settings used: statuses counted as posted: Posted; draw amount on the lender's form: 487,500.00; role asked about ledger differences: project accountant.

Totals: 5 required items: 2 complete, 2 incomplete, 1 missing. 1 optional item: 0 supplied. 4 missing attachments. 5 differences between the draw and the ledger, counting ledger entries not in the draw.

Checks that agree: The draw schedule has 6 invoices, each with a different invoice number. Invoices A-1101 and S-2207 agree with the ledger on payee, amount, budget line and status. For the 5 invoices found in the ledger, the payee agrees with the draw schedule. Items 3 and 5 each have a file name and a date. Every attachment row that names an invoice or a payee names one that is in the draw schedule.

A. Index in the lender's order
1. Cost: Invoice for each cost in the draw (each invoice). Incomplete, 5 of 6 invoices listed. Missing: M1.
2. Cost: Lien waiver for each payee (each payee). Incomplete, 4 of 6 payees listed. Missing: M2, M3.
3. Progress: Contractor's pay application (the draw). Complete: pay-app-5.pdf, dated 2026-11-02.
4. Progress: Inspection report for the period (the draw). Missing: M4.
5. Title: Title date-down report (the draw). Complete: title-date-down-oct.pdf, dated 2026-10-30.
6. Insurance: Insurance certificate update (the draw), optional. Not supplied.
Listed but not on the checklist: item 8, site-photos.zip, dated 2026-10-30.

B. Missing attachments
M1. Item 1, Invoice for each cost in the draw: invoice E-0188, Supplier E. Ask: Accounts payable.
M2. Item 2, Lien waiver for each payee: Supplier E. Ask: Project manager.
M3. Item 2, Lien waiver for each payee: Insurance Broker F. Ask: Project manager.
M4. Item 4, Inspection report for the period: the draw. Ask: Project manager.

C. Draw schedule against the ledger
D1. D-0415, Design Firm C: budget line is Soft costs in the draw and Hard costs in the ledger; amount 12,400.00 agrees. Ask: project accountant.
D2. P-3390, Supplier D: amount is 6,850.00 in the draw and 6,580.00 in the ledger; difference 270.00. Ask: project accountant.
D3. E-0188, Supplier E: 9,200.00, Site work, in the draw; not found in the ledger export. Ask: project accountant.
D4. F-0770, Insurance Broker F: ledger status is Entered, which is not a posted status; amount 4,300.00 and budget line agree. Ask: project accountant.
D5. S-2231, Supplier B: posted 2026-10-22 for 15,000.00, Site work, in the ledger; not in the draw schedule. Ask: project accountant.
By budget line (the draw's invoices by the draw's budget line; the ledger's entries for those same invoices by the ledger's budget line; difference is draw minus ledger):
- Hard costs: draw 412,500.00; ledger 424,900.00; difference -12,400.00 (D1).
- Site work: draw 47,450.00; ledger 38,250.00; difference 9,200.00 (D3).
- Soft costs: draw 23,550.00; ledger 10,880.00; difference 12,670.00 (D1, D2).
Total: draw 483,500.00; ledger 474,030.00; difference 9,470.00, made up of 9,200.00 not found (D3) and 270.00 in amount differences (D2).

D. Draw amount
The draw schedule totals 483,500.00. The lender's form shows 487,500.00. Difference 4,000.00, the form being higher. Ask: project finance lead.

Not checked: the contents of every attachment; lien status and title; the pay application's figures, which pay application line check covers; whether any amount is within the loan budget. These last two are listed because a reader might assume them checked.

The project finance lead approves submission. The lender decides funding. This index records which documents were listed, reads no document for its content, says nothing about lien status or title, submits nothing and changes no record.
```
