# Trial: Submittal register review, run on its invented example

- **Product:** Claude, run in Claude Code

Model: Claude Sonnet 5.5 (model ID claude-sonnet-5-5). The assistant that ran this trial did not write the template.

Date: 2026-11-10

The inputs are the invented example in `public/example.md` (a made-up two-storey annex, trades named Trade A to Trade H). No client data was used.

## Inputs used

The four inputs in the "The inputs" section of `public/example.md`: the settings, the required submittals (8 rows), the submittal log (9 rows) and the procurement dates (8 rows). No review period, resubmission days or long-lead threshold was given, so the three defaults applied.

One thing to know about this run: the template and the example were read in a single step, so the example's own output was already on screen before the assistant produced its own. The output below was worked out afresh from the inputs and every date and count was recomputed (weekdays checked with a calendar script), but this was not a blind run.

## What came out

The instruction block and the output format were followed as written.

```
SUBMITTAL REGISTER REVIEW: the Annex, Monday 16 November 2026

For: the project engineer. Prepared Monday 16 November 2026 from: required submittals (8 rows), submittal log (9 rows), procurement dates (8 rows), settings.
Column check: all headers matched.
Settings: review period 14 days, resubmission 7 days, long-lead threshold 56 days, counted in calendar days. Defaults used: review period, resubmission days, long-lead threshold.
Summary: 8 required submittals. Accepted 2 (approved 1, approved as noted 1). With reviewer 2. Received, not with reviewer 2. Returned 1. Not received 1. Submittals with missing documents: 4 (received 3, not received 1). Routing to verify: 4. Long-lead not yet accepted: 3, of which 1 at risk. At risk before the order date: 3; past the order date: 0. Substitutions requested and not accepted: 1.

Data checks
- S-09 is in the submittal log and is not on the required list. Left out of the register.

Register
- S-01 03 30 00 Concrete mix designs, Trade A. Revision 0 received Monday 12 October 2026. ACCEPTED: approved, recorded Friday 23 October 2026. Documents complete. Reviewer comment: "No comments".
- S-02 05 12 00 Structural steel shop drawings, Trade B. Revision 1 received Monday 9 November 2026. WITH REVIEWER since Tuesday 10 November 2026 (Structural reviewer), 6 days. Documents complete. Earlier revisions: revision 0 revise and resubmit, recorded Tuesday 27 October 2026. Long-lead, 70 days. Order by Monday 14 December 2026, 28 days away; review needs 14 days; 14 spare days.
- S-03 07 21 00 Roof insulation, Trade C. Revision 0 received Monday 2 November 2026. RECEIVED. Documents missing 1 of 2. Substitution requested. Order by Monday 7 December 2026, 21 days away; review and resubmission need 21 days; 0 spare days.
- S-04 08 11 13 Hollow metal doors and frames, Trade D. Revision 0 received Monday 26 October 2026. WITH REVIEWER since Tuesday 27 October 2026 (Architect's reviewer), 20 days. Documents complete. Order by Friday 27 November 2026, 11 days away; review needs 14 days; AT RISK, short 3 days.
- S-05 23 73 00 Air handling units, Trade E. Revision 0 received Monday 28 September 2026. ACCEPTED: approved as noted, recorded Monday 19 October 2026. Documents complete. Reviewer comment: "See the marked copy".
- S-06 26 24 16 Switchboards, Trade F. Revision 0 received Thursday 12 November 2026. RECEIVED. Documents missing 1 of 3. Long-lead, 112 days. Order by Wednesday 2 December 2026, 16 days away; review and resubmission need 21 days; AT RISK, short 5 days.
- S-07 09 30 00 Floor tile, Trade G. NOT RECEIVED. Documents missing 2 of 2. Order by Monday 23 November 2026, 7 days away; review and resubmission need 21 days; AT RISK, short 14 days.
- S-08 14 21 00 Passenger elevator, Trade H. Revision 0 received Monday 14 September 2026. RETURNED: rejected, recorded Friday 9 October 2026. Documents missing 1 of 3. Reviewer comment: "Cab finish samples required with resubmission". Long-lead, 168 days. Order by Monday 11 January 2027, 56 days away; review and resubmission need 21 days; 35 spare days.

Missing documents
- S-03 (Trade C): samples.
- S-06 (Trade F): coordination study.
- S-07 (Trade G): product data; samples. Nothing received.
- S-08 (Trade H): cab finish samples.

Routing to verify
- S-03: RECEIVED Monday 2 November 2026 with no reviewer recorded, 14 days.
- S-04: WITH REVIEWER since Tuesday 27 October 2026, 20 days, 6 days over the 14-day review period.
- S-06: RECEIVED Thursday 12 November 2026 with no reviewer recorded, 4 days.
- S-08: RETURNED Friday 9 October 2026 with no newer revision, 38 days since the status date. The log does not show whether the return reached the trade.

Long-lead items not yet accepted: 3
- S-06 Switchboards: AT RISK, short 5 days (order by Wednesday 2 December 2026). Received, not routed.
- S-02 Structural steel shop drawings: 14 spare days (order by Monday 14 December 2026). With the reviewer 6 days.
- S-08 Passenger elevator: 35 spare days (order by Monday 11 January 2027). Returned, no resubmission.

At risk before the order date: 3
- S-07 Floor tile: short 14 days; order by Monday 23 November 2026.
- S-06 Switchboards: short 5 days; order by Wednesday 2 December 2026.
- S-04 Hollow metal doors and frames: short 3 days; order by Friday 27 November 2026.

Questions for the project engineer
1. S-03 Roof insulation (Trade C). RECEIVED Monday 2 November 2026, product data only (samples missing), no reviewer recorded after 14 days; a substitution is marked requested. Order by Monday 7 December 2026, 21 days away, 21 days needed, 0 spare. What do you want done about routing and the missing samples?
2. S-04 Hollow metal doors and frames (Trade D). With the Architect's reviewer 20 days, 6 over the review period; documents complete. Order by Friday 27 November 2026, 11 days away against 14 needed, short 3 days. What do you want done?
3. S-06 Switchboards (Trade F). Received Thursday 12 November 2026 without the coordination study, no reviewer recorded, 4 days. Long-lead, 112 days. Order by Wednesday 2 December 2026, 16 days away against 21 needed, short 5 days. What do you want done about routing and the missing study?
4. S-07 Floor tile (Trade G). Not received; product data and samples missing. Order by Monday 23 November 2026, 7 days away against 21 needed, short 14 days. What do you want done?
5. S-08 Passenger elevator (Trade H). Rejected Friday 9 October 2026 with the comment "Cab finish samples required with resubmission"; no resubmission in 38 days. Long-lead, 168 days. Order by Monday 11 January 2027, 56 days away against 21 needed, 35 spare days. What do you want done?
Acceptance of each submittal rests with the authorized design reviewer; nothing here accepts a material, and releasing an order is purchasing's decision.

Draft for the project engineer's decisions. No trade, reviewer or supplier has been contacted, and no log, status or order has been changed.
```

## What was observed

- **Every required part was produced.** All sections of the output format are present, nothing stopped the run (the column check passed, no status word or date was invalid, no duplicates), and all counts agree with the lists.
- **No guessing was needed on the figures.** The statuses, missing documents, days, spare days, shortfalls, long-lead list and at-risk list came out the same as the published example's, including the sort orders.
- **Differences from the published example, all of wording or layout:**
  - The example writes some dates without the year ("Monday 12 October"); this run wrote the year every time, as the template's date rule reads.
  - The example adds "not routed" to the RECEIVED label on the register line; this run printed only "RECEIVED" there and left the routing to its own section.
  - The example adds "38 days ago" to the S-08 register line and "unrouted" to the routing days; this run did not.
  - The example's Data checks line also asks the project engineer to confirm the required list is complete; this run only stated the check.
  - The example's questions ask "Do you want to ..." with specific actions (ask Trade C for the samples, ask the reviewer for a date, tell purchasing). This run asked only "What do you want done?". The template says a question recommends nothing and offers no wording, so the example's phrasing is the closer call to a recommendation.
  - The example prints the S-06 note "coordination study missing" under long-lead; this run printed "Received, not routed".
- **Facts not in the inputs.** None found in this run or in the example's output; every figure traces to the inputs. One example line goes past the template: question 2 suggests telling purchasing the order date is at risk, which is a recommendation.
- **Where the instructions were ambiguous:**
  - For a package already WITH REVIEWER, "days needed" is the full review period even when days have already passed (S-02 has been with the reviewer 6 days; S-04 for 20, already over). The template states the rule plainly, so it was followed, but for S-04 it means a package already past the period is shown as needing another 14 days.
  - The register format has a "Long-lead" slot but does not say whether an accepted long-lead item (S-05, 98 days) carries it. This run left it off, as the example does, because the long-lead list excludes accepted items.
  - The status label is exactly as the log records it, but the format does not say whether a RECEIVED package with no reviewer should show "not routed" on its line. It is covered under Routing to verify, so it was left off.
  - The format's `[since ... ([reviewer]), [n] days]` does not say whether "days" counts from routing or from receipt; step 6 says routing, which was used.
  - The format shows "Reviewer comment" only for the latest package. An earlier revision's comment (S-02 revision 0: "See the marked drawings") is not printed, as the template says earlier revisions are noted only.
  - The "Routing to verify" and "Questions" parts overlap, so several lines repeat; this is by design but long.
  - A missing item on a RETURNED package (S-08) is counted under "Submittals with missing documents" and "Missing documents", although what is missing is a document the return asked for. That follows step 5 literally.
  - The template body says "Every thing the instructions require" (two words) in the output-format note.
- **Told to stop for anything?** No.
- **What this does not show.** This is one run, by one assistant, on invented data, with the example's output visible. It shows the instructions can be followed to the intended shape and figures. It does not test the template in a client environment, in another product, or against messy real exports.

## Edits made after this run, not run again

The output and observations above are as recorded and have not been changed. After the review of this template, these edits were made, and the template has not been run again on them:

- The published example now writes the year on every date, drops the words its output format has no slot for ("not routed", "38 days ago; no resubmission received", "unrouted") and drops the extra Data checks clause, as this run did.
- The example's questions now ask "What do you want done about [the matter]?" and name no action. Question 2 says "no decision recorded" in place of "no status recorded".
- The template states that days needed counts the full review period even for a package already with the reviewer, and lists that choice under what to customize.
- The format and the pasted instructions now say that an accepted long-lead item carries no Long-lead slot, and the question instruction says a question names the matter and no action.
- The typo "Every thing" is corrected.
- Later edits, also not run again: the pasted instructions now say to ask when a reviewer comment and a status disagree, to treat a package logged as received with no documents as missing every item (noted under Data checks), to treat an unreadable date such as "next week" as not supplied, and to name a resubmission among the matters a question may ask about; the register line's days are now labelled as counting from the routing date, which settles the fourth ambiguity above; and the example's "Trade H" in the routing note and question 5 became "the trade", as the template words it. The example's inputs and figures did not change.
