# Estimate basis pack: one run on its invented example

- **Product:** Claude, run in Claude Code
- **Model:** Claude Sonnet 5.5 (model ID claude-sonnet-5-5)
- **Date:** 2026-11-10

The inputs are the invented example in `public/example.md` (the drawing register, takeoff export, rates, quotes list, and settings and notes). No client data was used. This is the second run. The first, on the first version of the instructions, found the shortcomings listed at the end; the instructions, output format and example were revised after an independent review, and this run followed the revised instruction block, including the output format it now carries, as written.

One limit on this record: the run was made by the assistant that revised the template, with the example's inputs and its output both on screen. It was worked from the inputs and the instruction block, with every sum and date checked by calculation, but it was not a blind run.

Revision after review, same day. An independent review of this record made minor points. The template and example then changed in four ways: the scope-question rule now says that each distinct fact is its own cause and that a question about a line's quantity goes to the role in that line's takeoff_by column; the rate-with-no-line and differing-dates causes were split; the exclusion label "Prices:" became "Applies to:"; and the register date for A-101 became 2026-11-05 to match Addendum 1. Two lines of the output below changed as a result: the label, and question 7, whose answering role was "role to be named by the bid lead" and is now "the estimator", the C1 line's takeoff_by role. I then regenerated the pack from the revised instruction block and example and compared it with the earlier output; nothing else differs, and the sums were checked again. This regeneration was made by the same assistant that made the edits, with the earlier output on screen, so it is not a blind run, and a fresh-session run on the revised version is still wanted.

## What came out

ESTIMATE BASIS PACK: Unit 4 tenant fit-out

For: the estimator, the bid lead. Pricing date Tuesday 10 November 2026. Bid due Friday 20 November 2026, 12:00. Drawing set: A-101 rev C, A-501 rev B, A-601 rev B, M-101 rev A.

Basis checked: 4 sheets in the register. 10 takeoff lines. 9 rates. 3 quotes. Takeoff lines on a superseded drawing: F2. Quotes past their valid-to date: Q-B1. Quotes priced on a superseded drawing: Q-B1.

Worksheet:

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

Exclusions: 9

- Permit and inspection fees. Source: company standing exclusion. Applies to: all lines.
- Work outside the unit's demised area. Source: company standing exclusion. Applies to: all lines.
- Out-of-hours working. Source: company standing exclusion. Applies to: all lines.
- Painting. Source: Q-A1, Supplier A. Applies to: P1, P2, C1. The wording matches F2 (painting to partitions), which Q-C1 prices, so it is priced elsewhere.
- Fire-stopping above the ceiling line. Source: Q-A1, Supplier A. Applies to: P1, P2, C1. No wording match in a line description or a note.
- Installation (the quote is supply only). Source: Q-B1, Supplier B. Applies to: D1, D2. Addendum 1, item 3 says the doors are supplied and fitted. No other quote prices D1 or D2; see question 3.
- Hardware beyond the standard set. Source: Q-B1, Supplier B. Applies to: D1, D2. No wording match in a line description or a note.
- Preparation of damaged surfaces. Source: Q-C1, Supplier C. Applies to: F2. No wording match in a line description or a note.
- Work above 3.0 m height. Source: Q-C1, Supplier C. Applies to: F2. No wording match in a line description or a note.

Open scope questions: 9

1. D1, D2: Q-B1 priced A-501 rev A; the register's current revision is B (quotes list, register). Question: does the door price hold on rev B? Answered by: role to be named by the bid lead.
2. D1, D2: Q-B1 is valid to 2026-11-06; the pricing date is 2026-11-10 (quotes list, settings). Question: is the price still available, or is a refreshed quote needed? Answered by: role to be named by the bid lead.
3. D1, D2: Q-B1 is supply only (quotes list); Addendum 1, item 3 says the doors are supplied and fitted (notes). Question: who prices the fitting? Answered by: role to be named by the bid lead.
4. F2: the takeoff is on A-601 rev A; the register's current revision is B (takeoff, register); the quantity source is derived (takeoff). Question: does 454.0 m2 stand on rev B? Answered by: the estimator.
5. M1: no quantity, source "not yet measured" (takeoff). Question: how many diffusers are relocated? Answered by: the estimator.
6. M1: the only rate is historical, JOB-1182, dated 2026-03-12, 243 days before the pricing date; the limit is 90 days (rates, settings). Question: is the rate usable, or is a current rate to be supplied? Answered by: the estimator.
7. C1: the quantity source is assumed (takeoff); the notes say there is no reflected ceiling plan and that the ceiling area is the floor area from A-101 less the core, 190 m2 (notes). Question: is the ceiling area 190 m2? Answered by: the estimator.
8. J1: the rate is an allowance of 6,500.00 from "Estimator allowance", dated 2026-11-09 (rates). Question: does the allowance stand, or is a quote to be obtained? Answered by: the estimator.
9. E1: 34 outlets are counted; no rate row exists and no quote lists E1 in covers_items (rates, quotes list). Question: who prices the electrical work, or is it excluded? Answered by: role to be named by the bid lead.

Totals:

Figured lines: 8, 48,332.20. On lines with no flag: 24,023.00. On lines with a flag: 24,309.20. Lines with no figure: 2 (M1, E1).

Not included: overhead, profit, contingency, tax, bonds and anything else the bid lead adds.

To verify, estimator: all 8 figured lines against the drawings and the rate sources; flagged lines first: D1, D2, F2, C1, J1; lines with no figure: M1, E1.

Decisions for the bid lead: 3

1. Whether to submit with the five flagged lines (24,309.20 of the 48,332.20 figured) as they stand, or to wait for a refreshed Q-B1, a re-check of F2 on rev B and a ceiling area before Friday 20 November 2026, 12:00.
2. How M1 and E1 are carried in the figure: neither has a figure, M1 for want of a quantity and E1 for want of a rate.
3. Whether the 6,500.00 allowance for J1 stands in the submitted figure.

Every figure traces to the takeoff export, the rates export, the quotes list and the drawing register supplied for Unit 4 tenant fit-out. The pack sets no price, changes no record and sends nothing.

## What was observed

- All required parts were produced: the header, the basis line, the worksheet, exclusions, scope questions, totals, the verify list, the decisions and the trace line. No stop condition applied to these inputs.
- The eight amounts equal quantity times rate. The flagged and unflagged parts add to the figured total (24,023.00 plus 24,309.20 is 48,332.20). The rate ages (243 days for M1 and 70 days for F1, under the 90-day limit) were checked by calculation.
- Nine scope questions, one for each cause: the doors raise three (superseded quote, expired quote, supply only against the addendum) and M1 raises two (no quantity, old rate).
- M1 carries "assumed quantity" because its source, "not yet measured", is none of measured, counted or derived.
- Roles come only from the inputs: the estimator, and "role to be named by the bid lead" where the inputs name nobody. The pack names no purchasing lead or designer, and says nothing about how 454.0 m2 was derived beyond the takeoff's word "derived".
- The line figures, the nine exclusions, the totals and the three decisions are the same as in the first run.

## Shortcomings

Found in the first run, and fixed after it in the template and example; this run followed the fixed version:

- The role rule conflicted with the roles section and with the example's answers. Fixed: the rule and the roles section now agree, and the example uses only the roles in its inputs.
- An unlisted quantity source such as "not yet measured" had two readings. Fixed: it is shown as written inside an "assumed quantity" flag.
- No cause existed for an old rate or a unit mismatch, and it was unclear whether one line with several causes gets one question or several. Fixed: both are causes, and each cause gets its own question.
- It was not said which valid-to date decides expiry. Fixed: the quote's date decides, and a differing rate-row date raises a "valid-to dates differ" flag. This case does not occur in the example and has not been run.
- The text carried the placeholder "[your rate age limit]". Fixed: it reads the limit from the settings.

Seen in this run, not fixed: the example has no unit mismatch, no unreadable value, no rate with no line, no differing valid-to dates, no line covered twice, no quote missing from the quotes list and no drawing missing from the register, and no stop condition applied (headers, repeated ids and missing files all passed), so those rules have not been run.
