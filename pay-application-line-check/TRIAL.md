# Pay application line check: trial on the invented example

- **Product:** Claude, run in Claude Code
- **Model:** Claude Sonnet 5.5 (model ID claude-sonnet-5-5)
- **Date:** 2026-11-10

The inputs are the invented example in [example.md](example.md) ("Project Alpha", application 4). No client data was used. The run followed the fenced instruction block and the output format in the member template. The assistant that ran it had not written the template and read the example's inputs before its output.

## Inputs used

The five documents and three settings under "What the project accountant supplies" in [example.md](example.md): the pay application, the schedule of values, the change log, prior certificate 3 and the progress evidence; an evidence tolerance of 0.50 points, retainage of 5% of total completed and stored, and "Approved" as the approved status word.

## What came out

```
PAY APPLICATION LINE CHECK: Project Alpha, application 4, period to 31 October 2026

Prepared for: the project accountant. Basis: application 4 dated 2 November 2026; schedule of values (starting version); change log as of 31 October 2026; prior certificate 3 dated 2 October 2026; progress evidence from the superintendent log (30 October), inspection report (28 October), electrical inspection report (29 October) and delivery receipts (30 October).
Settings used: evidence tolerance 0.50 points; retainage 5% of total completed and stored; approved status word: Approved.

Totals: 5 lines checked. 11 differences: 8 on lines 02 to 05, 3 on page totals or page figures. Lines with no difference: 01.

Checks that agree: the application and schedule of values name the same project and application 4 follows certificate 3; line numbers are unique. Original contract sum 500,000 equals the schedule of values total. Scheduled values on lines 01, 02 and 03 equal the schedule of values plus approved changes. On every line except 04, previous plus this period plus stored equals the total shown; percent complete and balance follow from the totals shown on every line. Column totals for scheduled value, previous billed, this period, stored materials, total and balance equal the sums of their lines. Previous billed on lines 01 to 04 equals the prior certificate. Evidence on lines 01 and 03 agrees with the claim within tolerance. Retainage 16,300 equals 5% of 326,000; total earned less retainage 309,700 equals 326,000 less 16,300; current payment due 94,050 equals 309,700 less 215,650.

A. Arithmetic on the page
1. Line 04, total completed and stored: shown 46,000; the parts give 45,000 (27,000 + 18,000 + 0); difference 1,000. Percent complete 51.11 and balance 44,000 follow from the 46,000 shown. Ask: contractor's billing contact.
2. Totals row, total completed and stored: shown 326,000; the parts give 325,000 (227,000 + 86,000 + 12,000); difference 1,000. Follows from item 1.

B. Previous billing against the prior certificate
3. Line 05, previous billed: application 8,000; prior certificate 6,000; difference 2,000. The previous billed total of 227,000 is 2,000 above the certificate's 225,000 for the same reason. Ask: contractor's billing contact.

C. Changes against the schedule of values
4. CO-2, line 04: Approved, 6,000. Not on the application: scheduled value shown 90,000; schedule of values 90,000 plus 6,000 gives an expected 96,000. Ask: project manager.
5. CO-3, line 05: Pending, 9,000. Included on the application: scheduled value shown 89,000; schedule of values 80,000, and no approved change on this line, gives an expected 80,000. Ask: project manager.
6. Scheduled value total: shown 521,000; schedule of values 500,000 plus approved changes 18,000 gives 518,000; difference 3,000, being the 9,000 in item 5 less the 6,000 in item 4. Follows from items 4 and 5.

D. Progress evidence
7. Line 02: claimed 92.59% (150,000 over 162,000); evidence 92.00% (inspection report, 2026-10-28); 0.59 points above. Evidence implies 149,040; claimed 150,000; amount in question 960. Ask: superintendent.
8. Line 04: claimed 51.11% (46,000 over 90,000); evidence 40.00% (electrical inspection report, 2026-10-29); 11.11 points above. Evidence implies 36,000; claimed 46,000; amount in question 10,000. Ask: superintendent.
9. Line 05: no evidence supplied. Billed to date 16,000. Ask: superintendent.

E. Stored materials
10. Line 03: billed 12,000; supported 9,500 (superintendent log and delivery receipts, 2026-10-30); unsupported 2,500. Ask: superintendent.

F. Retainage and amount due
11. Less previous certificates for payment: application 215,650; prior certificate 213,750; difference 1,900. Follows from item 3.

Amount due as stated: 94,050. The page's own arithmetic from retainage to amount due agrees. This comparison does not restate it.

Not checked: Nothing left unchecked.

The project accountant verifies each figure against the documents. The authorized certifier decides payment and completion. This comparison certifies no completion percentage, interprets no contract term and changes no record.
```

## What was observed

- **Every required part was produced.** All six groups, the totals line, the checks that agree, the amount due as stated, the not-checked line and the decision line are present. Nothing triggered a stop: headers matched, every number was a number, the project and numbering agreed.
- **Eleven differences, the same eleven as the published example,** with the same figures: items 1 and 2 (line 04 total and the totals row), 3 (line 05 previous billed), 4 to 6 (CO-2, CO-3 and the scheduled value total), 7 to 9 (evidence on lines 02, 04 and 05), 10 (stored materials on line 03) and 11 (previous certificates, 1,900). The amounts in question, 960 and 10,000, and the unsupported 2,500 matched too. No fact appeared in either output that is not in the inputs or computed from them.
- **Differences from the published example.**
  - The example orders the evidence items line 04 first, then 02, then 05. The template says "for each line", so this run went in line order (02, 04, 05).
  - The example adds to item 5 that billed to date on line 05 is 20.00% of 80,000. The template does not ask for that, so this run left it out. The figure is correct (16,000 over 80,000).
  - The example's "Not checked" line says the 5% rate itself was not checked, as a contract matter. The template does not say to record that, so this run wrote "Nothing left unchecked", which is the template's own wording for the empty case.
  - The example's "Ask" on the stored materials item is the contractor's billing contact; this run asked the superintendent.
  - The example names the checks that agree in a slightly different order and omits the same-project and numbering check, which this run listed.
- **Where the instructions were ambiguous and a guess was needed.**
  - Who to ask for stored materials. The roles section makes the superintendent responsible for the progress evidence and the billing contact responsible for "the application's figures". Stored materials are both, so the choice was a guess.
  - The "Ask" for a follows-from item. The template says no second question, and this run left the Ask off, as the example does.
  - Item 11 says "Follows from item 3". That the 1,900 difference comes from the 2,000 previous billed difference needs the retainage rate (2,000 less 5%). The template does not say a follows-from link may rest on that inference. This run marked it, as the example does, but did not add the "(2,000 less 5%)" explanation.
  - The scheduled value total follows from two items, and the format allows only "Follows from item N". This run wrote "items 4 and 5".
  - The totals line splits differences between "on lines" and "on page totals". Item 11 and the scheduled value total fit neither exactly. This run counted item 4 and 5 as line items and items 2, 6 and 11 as totals or page figures.
  - The previous billed total note could be a separate item or part of item 3. The step says "say if", so it was folded into item 3 and not counted.
  - Evidence on line 04 can be measured against the 46,000 shown or the 45,000 the parts give. The template says to check the total as shown, so 46,000 was used for the claim.
  - Whether the claim should use the scheduled value as billed (162,000, 89,000) or the schedule of values plus approved changes. The template says to use scheduled value; this run used the application's.
- **Template text outside the instructions.** The acceptance tests are marked "proposed, none has been run". This trial ran only the example, not those tests.
- **Limits.** One run, one invented example, one product. It shows the instructions can be followed to a page that agrees with the example. It says nothing about messy real exports, other products or other projects.

## Changed after the run

The output and observations above are as recorded and describe the template and the example as they stood at the run. After an independent review on 10 November 2026 the template, the example and the public profile were changed as listed below, and the template was not run again. Nothing in the recorded output was altered.

- **Prior certificate amount.** The template and the instruction block now call it the total earned less retainage on the prior certificate (the cumulative amount certified to date, not that period's payment). The example's input says so.
- **Evidence in line order.** The example now lists the evidence items in line order (02, 04, 05), as this run did.
- **Extra figure and expected value.** The example no longer adds the 20.00% figure to item 5 and states the expected scheduled value of 80,000, as this run did.
- **Stored materials role.** The template, the output format and the example now ask the superintendent, as this run did.
- **Several causes.** The format and instruction block allow "Follows from items N and M", as this run wrote for the scheduled value total.
- **Totals line.** The split is now defined as differences on a line of the application and differences on page figures (the totals row, the scheduled value total and the application's own fields). The label is "page figures"; this run wrote "page totals or page figures".
- **Basis of the claim.** The template states that the evidence comparison uses the application's scheduled value, as this run assumed.
- **Fallbacks.** The instruction block now carries the change log, prior certificate and evidence not supplied cases, a line not in the schedule of values or the change log, stored materials with no support row, and a status word not in the approved list.
- **Retainage rate.** Step 10 and the instruction block now say a supplied rate is used as supplied and not checked against the contract, and the format's "Not checked" line carries it. This run wrote "Nothing left unchecked", which the template no longer produces when a rate is supplied.
- **Example wording.** The example says "shown" where the format does, and item 11 no longer carries the explanation "(2,000 less 5%)", which this run also left out.
- **Second round of minor points (10 November 2026, after the independent review).** The example inputs now name Project Alpha in each document's heading, so the same-project check has something to read; this run's line "the application and schedule of values name the same project" rests on the intro only, and is left as recorded. The example output now says "no evidence supplied" as the format does, drops "over the 0.50 tolerance" from item 7 and words the stored materials source as the format does. The instruction block gained a line telling the reader to paste the output format with it, the application-number-in-sequence check, the password handling, the position of "Checks that agree" and the allowance that a follows-from link may rest on a calculation through a supplied setting (step 8 of the procedure says the same). These additions were not run again; the recorded output is unaltered.
- **Profile.** The public profile says the template was tried once and points to this record; "job" was replaced by "project".
