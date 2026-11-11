# Trial: Punch list consolidation, run on its invented example

- **Product:** Claude, run in Claude Code

Model: Claude Sonnet 5.5 (model ID claude-sonnet-5-5). The assistant that ran this trial did not write the template.

Date: 2026-11-10

The inputs are the invented example in `public/example.md` (the Lakeside Annex, a made-up two-storey building, with trades named Trade A to Trade F). No client data was used.

## Inputs used

The four invented inputs from `public/example.md`: the settings, the prior punch list (6 rows), the walk notes (8 rows) and the contractor updates (4 rows). Nothing else was supplied, so the default of 7 follow-up days applied and no next walk date was given. The example's own output was not read until after the output below was produced.

## What came out

The instruction block and output format were followed as written. This is the output in full.

```
PUNCH LIST CONSOLIDATION: the Lakeside Annex, walk of Tuesday 17 November 2026

For: the site manager. Prepared Tuesday 17 November 2026 from: prior punch list (6 rows), walk notes (8 rows), contractor updates (4 rows), settings.
Column check: all headers matched.
Settings: walk date Tuesday 17 November 2026, follow-up 7 days, next walk not supplied, target closeout Friday 11 December 2026, counted in calendar days. Defaults used: follow-up days.
Summary: 9 items. Open 7 (overdue 3). Contractor reports complete, awaiting verification 1. Verified closed 1. Raised again at the walk 2. Walk notes 8: merged into existing items 5, new items 3. Contractor updates attached 4. Possible duplicates not merged 1 pair. Items with no photograph 2. Trade not stated 1. Proposed follow-up dates 8 (trade's own date 3, existing due date 0, next walk 0, default 4, verification 1); after target closeout 0.

Data checks
- Update U-04 has no item number. It was attached to P-05, the only item not verified closed with the same location and trade (Level 2 Room 2.02, Trade A).
- Walk note W-07 has no trade. Its item, NEW-3, is listed under "Trade not stated".
- P-06 has no due date. None was invented.
- No "verified closed" row is missing its verifier or date.
- No walk note or update uses the words "unsafe", "hazard" or "danger".
- Location and trade names: no item was found written in several ways.

Punch list

Level 1 Corridor

Trade A

- P-01 Touch-up paint scuffs on north wall. OPEN. Overdue by 4 days (due Friday 13 November). Merged: P-01, W-01 (same text). Update U-01, Monday 16 November: "Touch-up scheduled", promised Friday 20 November. Evidence: IMG-101 (walk, Tuesday 17 November). Proposed follow-up: Friday 20 November (trade's date), 7 days later than the existing due date.

Level 1 Room 1.04

Trade B

- P-02 Replace cracked floor tile at doorway. OPEN. Overdue by 4 days (due Friday 13 November). Raised again at the walk, Tuesday 17 November: "Tile at doorway has cracked again along the grout line". Merged: P-02, W-02 (the walk note names P-02). Earlier contractor note: "Replaced 12 Nov". Evidence: IMG-102 (walk, Tuesday 17 November). Proposed follow-up: Tuesday 24 November (default, walk date plus 7 days), 11 days later than the existing due date.

Trade C

- P-03 Door closer does not latch. VERIFIED CLOSED: Quality lead, Thursday 12 November 2026. Raised again at the walk, Tuesday 17 November, with the same wording. Merged: P-03, W-06 (the walk note names P-03; the text also matches). Evidence: IMG-105 (walk, Tuesday 17 November). Proposed follow-up: none until the site manager decides.

Level 2 Room 2.01

Trade D

- P-04 Missing cover plate on data outlet. OPEN. Due Friday 20 November. Merged: P-04, W-03 (same text). Update U-02, Monday 16 November: "Cover plate on order", promised Wednesday 25 November. Evidence: IMG-103 (walk, Tuesday 17 November). Proposed follow-up: Wednesday 25 November (trade's date), 5 days later than the existing due date.

Trade F

- NEW-1 Ceiling tile stained above desk position 3. OPEN. Merged: W-04. Evidence: IMG-104 (walk, Tuesday 17 November). Possible duplicate of NEW-2. Proposed follow-up: Tuesday 24 November (default, walk date plus 7 days).
- NEW-2 Stained ceiling tile above desk 3. OPEN. Merged: W-05. No photograph supplied. Possible duplicate of NEW-1. Proposed follow-up: Tuesday 24 November (default, walk date plus 7 days).

Level 2 Room 2.02

Trade A

- P-05 Seal gap at window sill. OPEN. Overdue by 7 days (due Tuesday 10 November). Merged: P-05, W-08 (same text). Update U-04, Monday 16 November: "Sealant to be applied Thursday", promised Thursday 19 November (attached by location and trade, no item number). No photograph supplied. Proposed follow-up: Thursday 19 November (trade's date), 9 days later than the existing due date.

Level 2 Stair

Trade not stated

- NEW-3 Handrail loose at lower bracket. OPEN. Merged: W-07. Evidence: IMG-106 (walk, Tuesday 17 November). Proposed follow-up: Tuesday 24 November (default, walk date plus 7 days).

Roof

Trade E

- P-06 Clear debris from roof drain. CONTRACTOR REPORTS COMPLETE, not verified. Update U-03, Monday 16 November: "Drain cleared and debris removed", reports complete. Evidence: IMG-107 (contractor update, Monday 16 November). No due date recorded. Proposed follow-up: Tuesday 24 November (verification check; default, walk date plus 7 days).

Possible duplicates, not merged: 1 pair
- NEW-1 and NEW-2, Level 2 Room 2.01, Trade F. Same location and trade, different wording: "Ceiling tile stained above desk position 3" and "Stained ceiling tile above desk 3".

Raised again at the walk: 2
- P-02, recorded as reported complete ("Replaced 12 Nov"), seen again Tuesday 17 November. Label now shown: OPEN.
- P-03, verified closed by the Quality lead on Thursday 12 November 2026, seen again Tuesday 17 November. Label now shown: VERIFIED CLOSED (not reopened).

Reported complete, awaiting verification: 1
- P-06 Clear debris from roof drain (Trade E): reported Monday 16 November, with IMG-107. Proposed check Tuesday 24 November.

Overdue open items: 3
- P-05 Seal gap at window sill: 7 days (due Tuesday 10 November).
- P-01 Touch-up paint scuffs on north wall: 4 days (due Friday 13 November).
- P-02 Replace cracked floor tile at doorway: 4 days (due Friday 13 November).

Items with no photograph: 2
- P-05 Seal gap at window sill (Level 2 Room 2.02, Trade A).
- NEW-2 Stained ceiling tile above desk 3 (Level 2 Room 2.01, Trade F).

Questions for the site manager
1. P-01 Touch-up paint scuffs on north wall (Trade A). Open, due Friday 13 November, now 4 days overdue. Trade A's update of Monday 16 November says "Touch-up scheduled", promised Friday 20 November, 7 days after the due date. What date do you want to set?
2. P-02 Replace cracked floor tile at doorway (Trade B). The prior list records Trade B's note "Replaced 12 Nov" and reported complete; the walk on Tuesday 17 November recorded "Tile at doorway has cracked again along the grout line" (IMG-102). It is shown as OPEN, 4 days past its due date of Friday 13 November. The proposed check of Tuesday 24 November is 11 days after that date. What do you want done?
3. P-03 Door closer does not latch (Trade C). Verified closed by the Quality lead on Thursday 12 November 2026; the walk on Tuesday 17 November recorded the same wording (IMG-105). It still shows as VERIFIED CLOSED. What do you want done?
4. P-04 Missing cover plate on data outlet (Trade D). Due Friday 20 November; Trade D promises Wednesday 25 November, 5 days later. The target closeout is Friday 11 December. What date do you want to set?
5. P-05 Seal gap at window sill (Trade A). Open, due Tuesday 10 November, now 7 days overdue; no photograph. Trade A's update (no item number, matched by location and trade) says "Sealant to be applied Thursday", promised Thursday 19 November, 9 days after the due date. What do you want done?
6. P-06 Clear debris from roof drain (Trade E). Trade E reported it complete on Monday 16 November, with IMG-107. Nobody has verified it. What do you want done?
7. NEW-1 and NEW-2 (Level 2 Room 2.01, Trade F). Same location and trade, different wording: "Ceiling tile stained above desk position 3" (IMG-104) and "Stained ceiling tile above desk 3" (no photograph). What do you want done with the pair?
8. NEW-3 Handrail loose at lower bracket (Level 2 Stair). The walk note states no trade. What do you want done?

Completion is accepted only by the authorized inspector or owner representative; a trade's note that work is complete is not verified closure; and assigning the work is the site manager's decision.

Draft for the site manager's decisions. No trade, inspector or owner representative has been contacted, and no punch list, status or due date has been changed.
```

## What was observed

- Every part of the output format was produced, including the Summary counts, which agree with the list (7 open, 1 reported complete, 1 verified closed, 9 items; 8 proposed dates, none for the raised-again closed item).
- Nothing in the inputs caused a stop. The column check passed, every status word and date was valid, no duplicate or unknown item numbers.
- Ambiguities and guesses:
  - P-02 was recorded as reported complete, then seen again at the walk, so it became OPEN. Step 9 says items reported complete are not overdue, but its due date had passed and its new label was OPEN, so it was counted as overdue. The template does not say which rule wins.
  - The "Raised again at the walk" count was taken to cover only the two items the steps name (verified closed, and reported complete). Walk notes that matched open items (W-01, W-03, W-08) were not counted. The template does not say so directly.
  - W-06 matched P-03 both by `refers_to` and by text. The template does not say which "how merged" to print, so both were stated.
  - P-06 is both a default-date item and a verification check. The summary breakdown lists "default" and "verification" separately, so it was counted once, under verification, so that the parts add up to 8. The template does not say how.
  - The summary breakdown has a "next walk" count in the format; it was kept at 0.
  - New items have no due date. The "No due date recorded" phrase and the Data check for a missing due date are written for prior items only, so neither was printed for them.
  - A loose handrail (NEW-3) may be a safety concern, but the danger-wording check is a word match only ("unsafe", "hazard", "danger"), so nothing was flagged. This was left as the template says, and no judgement was made.
  - The format's "For: [decider role]" was filled from the settings line "Decides: the site manager".
  - The question rule requires a question for every item with a proposed date later than its existing due date. In this run that also covered P-01, P-02 and P-05, which already had questions for being overdue.
  - The rule that questions "recommend nothing" left the questions rather thin ("What do you want done?"). That is as written but gives the site manager little to react to.
- The recorded output omits the year on most dates (for example "due Friday 13 November"), where the output format requires it (for example "Tuesday 17 November 2026"). The statement above that the format was followed as written does not hold for dates. The output is left as recorded.
- Nothing was told to stop for and nothing was declined.
- No fact was added that is not in the inputs. Weekdays and day counts were worked out from the calendar.

### Differences from the published example

After producing the output above, it was compared with the example's output and the template's reviewer checklist.

- The items, groups, statuses, merges, counts, overdue days and proposed dates are the same.
- The example omits the "n days later than the existing due date" note on P-01 (7 days), P-02 (11 days) and P-05 (9 days). Step 10 requires it wherever the proposed date is later, and it appears only on P-04 in the example.
- The example's summary basis list leaves out "next walk 0", which the output format includes.
- The example's questions suggest actions: it asks whether to "assign it back to Trade B" for P-02, whether to have P-03 "reopened under the same number, logged as a new item, or checked with the Quality lead first", and whether to "ask for a photograph with the next update" for P-05. Step 12 says a question recommends nothing, and the closing line says assigning is the site manager's decision. This run's questions are plainer and follow that rule more strictly.
- The example does not print the verified date with the year for P-03 or mention that W-06 also matches by text. It prints "Merged: P-05, W-08 (same text), U-04 (same location and trade)", while this run listed the update separately on its own line.
- Data checks differ in wording; the example says only that no unsafe words were found and does not state the other empty checks.
- Every fact in the example's output is in the inputs, apart from the template's own standard phrases.

### Template defects, in short

1. Step 9 (reported complete items are not overdue) and step 6 (a reported-complete item seen again becomes OPEN) overlap for P-02 without a stated order.
2. "Raised again at the walk" is not defined for walk notes on items that were already open.
3. The summary's follow-up breakdown lists default and verification as separate bases, but a verification date also uses the default.
4. No rule for the "No due date recorded" note on new items.
5. When a walk note matches an item both by `refers_to` and by text, the template does not say which is shown.
6. The published example breaks two of the template's own rules: the later-than-due-date note, and the "recommends nothing" rule for questions.

## Edits made after this run, and not run again

The output and observations above are as recorded. After an independent review, on 10 November 2026, the template and the example were edited in small ways that have not been run again:

- The published example was corrected by hand, not re-run, to match the template: the "later than the existing due date" note on P-01, P-02 and P-05; "next walk 0" in the Summary; the Data checks for a verified closed row missing its verifier and for locations or trades written several ways; years on every date; and plainer questions that state facts and recommend nothing, with the trade's own words in question 1. The example's inputs are unchanged.
- Step 6 now says it applies before step 9, so a reported-complete item seen again at the walk is OPEN and then tested for overdue (defect 1 above).
- Step 6 now says a walk note merged into an item that was already open is not counted as raised again (defect 2).
- Step 10 now says a verification date is counted only under verification in the Summary (defect 3).
- Step 2 now says new items never have a due date, so "No due date recorded" and the missing-due-date check are for prior items only (defect 4).
- Step 4 now says that when a walk note matches both by `refers_to` and by text, "the walk note names [item]" is printed (defect 5).
- Step 7 now marks possible duplicates only among items that are not verified closed.
- The pasted instructions carry all of the above, and now also carry the two exceptions on a walk note and update that disagree and on a location or trade written several ways.
- After a later independent review, small clarifications were made and not run again: step 2 lists a location or trade written several ways among the Data checks; step 6 says an open item with an update reporting complete and a walk note of the same or a later date stays open and is not counted as raised again; the pasted instructions now include a `reports_complete` that is neither yes nor no among the stops, "if there are none of that kind, say so" in the danger-wording check, and the step 6 clarification; and the example no longer prints "the text also matches" for P-03 or the update basis inside the merge list for P-05.
- The profile now says the danger-wording check matches only the words listed, so a loose handrail is not flagged by it.
