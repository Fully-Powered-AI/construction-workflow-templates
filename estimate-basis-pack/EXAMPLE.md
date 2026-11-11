# Estimate basis pack: an invented example

*Illustrative example with invented data.* The company, the people, the suppliers, the drawings, the quantities and every price below are invented. The company is an invented general contractor pricing the fit-out of one small tenant unit. The estimator prepares the price and the bid lead decides the figure to submit; people are named by role only. On Tuesday 10 November 2026 the estimator supplied the five inputs below, in full, and got back the pack that follows.

## The inputs

### 1. Drawing register

```
sheet,title,revision,date,status
A-101,Floor plan,C,2026-11-05,Issued for bid
A-501,Partition and door schedule,B,2026-10-28,Issued for bid
A-601,Finish schedule,B,2026-10-28,Issued for bid
M-101,Mechanical plan,A,2026-10-20,Issued for bid
```

### 2. Takeoff export

```
section,item_id,description,unit,quantity,quantity_source,drawing_ref,revision,takeoff_by
Partitions,P1,"Metal stud partition, one layer of board each side, 90 mm",m2,185.0,measured,A-501,B,Estimator
Partitions,P2,"Acoustic partition, double layer",m2,42.0,measured,A-501,B,Estimator
Doors,D1,"Hollow metal door and frame, single",each,6,counted,A-501,B,Estimator
Doors,D2,"Glazed door, single",each,2,counted,A-501,B,Estimator
Finishes,F1,Vinyl plank flooring,m2,210.0,measured,A-601,B,Estimator
Finishes,F2,"Painting to partitions, two coats",m2,454.0,derived,A-601,A,Estimator
Mechanical,M1,Relocate supply diffusers,each,,not yet measured,M-101,A,Estimator
Ceilings,C1,Suspended ceiling tile and grid,m2,190.0,assumed,A-101,C,Estimator
Joinery,J1,Reception counter,item,1,counted,A-101,C,Estimator
Electrical,E1,Power and data outlets,each,34,counted,A-101,C,Estimator
```

### 3. Rates

```
item_id,rate,rate_unit,rate_source,source_ref,source_date,valid_until
P1,58.00,m2,supplier quote,Q-A1,2026-11-02,2026-11-30
P2,84.00,m2,supplier quote,Q-A1,2026-11-02,2026-11-30
D1,640.00,each,supplier quote,Q-B1,2026-10-15,2026-11-06
D2,1150.00,each,supplier quote,Q-B1,2026-10-15,2026-11-06
F1,46.50,m2,price book,PB-2026-09,2026-09-01,
F2,9.80,m2,supplier quote,Q-C1,2026-11-03,2026-12-03
M1,310.00,each,historical,JOB-1182,2026-03-12,
C1,38.00,m2,supplier quote,Q-A1,2026-11-02,2026-11-30
J1,6500.00,item,allowance,Estimator allowance,2026-11-09,
```

### 4. Quotes list

```
quote_id,supplier,quote_date,valid_until,drawings_priced,covers_items,inclusions,exclusions
Q-A1,Supplier A,2026-11-02,2026-11-30,A-501 B; A-101 C,P1; P2; C1,Supply and install,Painting; fire-stopping above the ceiling line
Q-B1,Supplier B,2026-10-15,2026-11-06,A-501 A,D1; D2,Supply only,Hardware beyond the standard set
Q-C1,Supplier C,2026-11-03,2026-12-03,A-601 B,F2,Labour and paint,Preparation of damaged surfaces; work above 3.0 m height
```

### 5. Settings and notes

```
Job: Unit 4 tenant fit-out
Currency: dollars
Pricing date: Tuesday 10 November 2026
Bid due: Friday 20 November 2026, 12:00
Estimator: the estimator. Bid lead: the bid lead.
Rate age limit: 90 days
Standing exclusions: Permit and inspection fees; Work outside the unit's demised area; Out-of-hours working
Notes:
- Addendum 1 (5 November) reissued A-101 as revision C; the reception counter moved.
- Addendum 1, item 3: doors are to be supplied and fitted.
- There is no reflected ceiling plan in the set. The ceiling area is the floor area from A-101 less the core, 190 m2.
- The bid lead adds overhead, profit and contingency.
```

## The output

**ESTIMATE BASIS PACK: Unit 4 tenant fit-out**

**For:** the estimator, the bid lead. Pricing date Tuesday 10 November 2026. Bid due Friday 20 November 2026, 12:00. Drawing set: A-101 rev C, A-501 rev B, A-601 rev B, M-101 rev A.

**Basis checked:** 4 sheets in the register. 10 takeoff lines. 9 rates. 3 quotes. Takeoff lines on a superseded drawing: F2. Quotes past their valid-to date: Q-B1. Quotes priced on a superseded drawing: Q-B1.

**Worksheet:**

Partitions  
P1 Metal stud partition, one layer of board each side, 90 mm. Quantity 185.0 m2 (measured; A-501 rev B). Rate 58.00/m2 (supplier quote, Q-A1, dated 2026-11-02, valid to 2026-11-30). Amount 10,730.00. Flags: none.  
P2 Acoustic partition, double layer. Quantity 42.0 m2 (measured; A-501 rev B). Rate 84.00/m2 (supplier quote, Q-A1, dated 2026-11-02, valid to 2026-11-30). Amount 3,528.00. Flags: none.  

Doors  
D1 Hollow metal door and frame, single. Quantity 6 each (counted; A-501 rev B). Rate 640.00/each (supplier quote, Q-B1, dated 2026-10-15, valid to 2026-11-06). Amount 3,840.00. Flags: expired quote (valid to 2026-11-06, pricing date 2026-11-10); quote on superseded drawing (Q-B1 priced A-501 rev A, current rev B).  
D2 Glazed door, single. Quantity 2 each (counted; A-501 rev B). Rate 1,150.00/each (supplier quote, Q-B1, dated 2026-10-15, valid to 2026-11-06). Amount 2,300.00. Flags: expired quote (valid to 2026-11-06, pricing date 2026-11-10); quote on superseded drawing (Q-B1 priced A-501 rev A, current rev B).  

Finishes  
F1 Vinyl plank flooring. Quantity 210.0 m2 (measured; A-601 rev B). Rate 46.50/m2 (price book, PB-2026-09, dated 2026-09-01, no valid-to date). Amount 9,765.00. Flags: none.  
F2 Painting to partitions, two coats. Quantity 454.0 m2 (derived; A-601 rev A). Rate 9.80/m2 (supplier quote, Q-C1, dated 2026-11-03, valid to 2026-12-03). Amount 4,449.20. Flags: superseded drawing (takeoff taken from A-601 rev A, current rev B).  

Mechanical  
M1 Relocate supply diffusers. Quantity not given (not yet measured; M-101 rev A). Rate 310.00/each (historical, JOB-1182, dated 2026-03-12, no valid-to date). Amount: no figure. Flags: no quantity; assumed quantity (source "not yet measured", not measured, counted or derived; estimator to classify); old rate (243 days before the pricing date, limit 90).  

Ceilings  
C1 Suspended ceiling tile and grid. Quantity 190.0 m2 (assumed; A-101 rev C). Rate 38.00/m2 (supplier quote, Q-A1, dated 2026-11-02, valid to 2026-11-30). Amount 7,220.00. Flags: assumed quantity.  

Joinery  
J1 Reception counter. Quantity 1 item (counted; A-101 rev C). Rate 6,500.00/item (allowance, Estimator allowance, dated 2026-11-09, no valid-to date). Amount 6,500.00. Flags: allowance.  

Electrical  
E1 Power and data outlets. Quantity 34 each (counted; A-101 rev C). Rate none supplied. Amount: no figure. Flags: no rate.  

**Exclusions:** 9

- Permit and inspection fees. Source: company standing exclusion. Applies to: all lines.
- Work outside the unit's demised area. Source: company standing exclusion. Applies to: all lines.
- Out-of-hours working. Source: company standing exclusion. Applies to: all lines.
- Painting. Source: Q-A1, Supplier A. Applies to: P1, P2, C1. The wording matches F2 (painting to partitions), which Q-C1 prices, so it is priced elsewhere.
- Fire-stopping above the ceiling line. Source: Q-A1, Supplier A. Applies to: P1, P2, C1. No wording match in a line description or a note.
- Installation (the quote is supply only). Source: Q-B1, Supplier B. Applies to: D1, D2. Addendum 1, item 3 says the doors are supplied and fitted. No other quote prices D1 or D2; see question 3.
- Hardware beyond the standard set. Source: Q-B1, Supplier B. Applies to: D1, D2. No wording match in a line description or a note.
- Preparation of damaged surfaces. Source: Q-C1, Supplier C. Applies to: F2. No wording match in a line description or a note.
- Work above 3.0 m height. Source: Q-C1, Supplier C. Applies to: F2. No wording match in a line description or a note.

**Open scope questions:** 9

1. D1, D2: Q-B1 priced A-501 rev A; the register's current revision is B (quotes list, register). Question: does the door price hold on rev B? Answered by: role to be named by the bid lead.
2. D1, D2: Q-B1 is valid to 2026-11-06; the pricing date is 2026-11-10 (quotes list, settings). Question: is the price still available, or is a refreshed quote needed? Answered by: role to be named by the bid lead.
3. D1, D2: Q-B1 is supply only (quotes list); Addendum 1, item 3 says the doors are supplied and fitted (notes). Question: who prices the fitting? Answered by: role to be named by the bid lead.
4. F2: the takeoff is on A-601 rev A; the register's current revision is B (takeoff, register); the quantity source is derived (takeoff). Question: does 454.0 m2 stand on rev B? Answered by: the estimator.
5. M1: no quantity, source "not yet measured" (takeoff). Question: how many diffusers are relocated? Answered by: the estimator.
6. M1: the only rate is historical, JOB-1182, dated 2026-03-12, 243 days before the pricing date; the limit is 90 days (rates, settings). Question: is the rate usable, or is a current rate to be supplied? Answered by: the estimator.
7. C1: the quantity source is assumed (takeoff); the notes say there is no reflected ceiling plan and that the ceiling area is the floor area from A-101 less the core, 190 m2 (notes). Question: is the ceiling area 190 m2? Answered by: the estimator.
8. J1: the rate is an allowance of 6,500.00 from "Estimator allowance", dated 2026-11-09 (rates). Question: does the allowance stand, or is a quote to be obtained? Answered by: the estimator.
9. E1: 34 outlets are counted; no rate row exists and no quote lists E1 in covers_items (rates, quotes list). Question: who prices the electrical work, or is it excluded? Answered by: role to be named by the bid lead.

**Totals:**

Figured lines: 8, 48,332.20. On lines with no flag: 24,023.00. On lines with a flag: 24,309.20. Lines with no figure: 2 (M1, E1).

Not included: overhead, profit, contingency, tax, bonds and anything else the bid lead adds.

**To verify, estimator:** all 8 figured lines against the drawings and the rate sources; flagged lines first: D1, D2, F2, C1, J1; lines with no figure: M1, E1.

**Decisions for the bid lead:** 3

1. Whether to submit with the five flagged lines (24,309.20 of the 48,332.20 figured) as they stand, or to wait for a refreshed Q-B1, a re-check of F2 on rev B and a ceiling area before Friday 20 November 2026, 12:00.
2. How M1 and E1 are carried in the figure: neither has a figure, M1 for want of a quantity and E1 for want of a rate.
3. Whether the 6,500.00 allowance for J1 stands in the submitted figure.

Every figure traces to the takeoff export, the rates export, the quotes list and the drawing register supplied for Unit 4 tenant fit-out. The pack sets no price, changes no record and sends nothing.
