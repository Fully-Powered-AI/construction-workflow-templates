# Three-week look-ahead constraint review: one trial on the invented example

- **Product:** Claude, run in Claude Code
- **Model:** Claude Sonnet 5.5 (model ID claude-sonnet-5-5)
- **Date:** 2026-11-10

The inputs are the invented example published beside this record (`example.md`, section "The inputs": settings, schedule extract, trade updates, deliveries, RFI log, approvals and submittals log, access claims). No client data was used. The model that ran this trial did not write the template. It read the template and the example's inputs first, followed the instruction block and the output format, produced the brief, and only then read the example's published output to compare.

This is one run by one model on one example. It shows what happened this once. It is not a test in a client environment.

## What came out

The brief is given in full below, in the template's output format.

THREE-WEEK LOOK-AHEAD CONSTRAINT REVIEW: Marlow Yard Block C interior fit-out

For: Superintendent. Prepared by: Project engineer. Check date: Thursday 12 November 2026. Meeting: Friday 13 November 2026.
Window: Thursday 12 November 2026 to Wednesday 2 December 2026 (3 weeks). Working days: Monday to Friday. Closed days in the window: Thursday 26 November 2026, Friday 27 November 2026.
Supplied: schedule (11 activities); trade updates (9 rows, 1 superseded); deliveries (7 rows); RFIs (5 rows); approvals (5 rows); access claims (6 rows).
Not supplied: none. Checks not made because of it: none.
Activities in the window: 9. Left out: 2. Activities with a constraint: 9.
Items to chase: approvals 4, deliveries 3, RFIs 4.

ALREADY UNDER WAY OR PAST ITS FINISH

A104 Level 3 west framing. Framing A, Level 3 west. Scheduled Monday 2 November to Wednesday 11 November. Status: in progress. Waits on: nothing.
  Trade update: Wednesday 11 November, Monday 2 November to Friday 13 November, crew 5, note: "Two walls on hold for RFI-014".
  Constraints:
  Dates: scheduled finish Wednesday 11 November has passed and the activity is not complete, 1 working day past. Framing A reports finish Friday 13 November, 2 working days later than scheduled.
  Overlap: O2, with A105.
  RFI: RFI-014, open, needed by Friday 6 November, overdue by 4 working days.

A101 Level 2 east ceiling duct rough-in. Mechanical A, Level 2 east. Scheduled Monday 9 November to Tuesday 17 November. Status: in progress. Waits on: A100.
  Trade update: Tuesday 10 November, Monday 9 November to Thursday 19 November, crew 4, note: "Crew of 4; no second shift".
  Constraints:
  Dates: Mechanical A reports finish Thursday 19 November, 2 working days later than scheduled.
  Overlap: O1, with A102.

WEEK 1: Thursday 12 November to Wednesday 18 November

A102 Level 2 east electrical rough-in. Electrical A, Level 2 east. Scheduled Thursday 12 November to Friday 20 November. Status: not started. Waits on: A100.
  Trade update: Wednesday 11 November, Thursday 12 November to Friday 20 November, crew 3, no note.
  Constraints:
  Overlap: O1, with A101.

A105 Level 3 west electrical rough-in. Electrical A, Level 3 west. Scheduled Thursday 12 November to Tuesday 24 November. Status: not started. Waits on: A104.
  Trade update: none on file.
  Constraints:
  Waits on unfinished work: A104 is in progress. Both tests apply. Its scheduled finish, Wednesday 11 November, is before the check date; and its later finish, the reported Friday 13 November, is after A105's scheduled start, Thursday 12 November.
  Trade update: no trade update on file.
  Overlap: O2, with A104; O3, with A109.
  Approval: S03, not submitted, needed by Wednesday 11 November, overdue by 1 working day. Nothing has gone to the reviewer.

A106 Ground floor storefront glazing install. Glazing A, Ground floor front. Scheduled Monday 16 November to Friday 20 November. Status: not started. Waits on: nothing.
  Trade update: stale: Monday 2 November, Monday 16 November to Friday 20 November, crew 4, no note.
  Constraints:
  Trade update: stale update, 10 days before the check date.
  Approval: S01, revise and resubmit, needed by Friday 6 November, overdue by 4 working days. Back with the submitter.
  Delivery: D01, promised after the date needed, 6 working days late.

A109 Level 3 west duct rough-in. Mechanical A, Level 3 west. Scheduled Tuesday 17 November to Wednesday 25 November. Status: not started. Waits on: A104.
  Trade update: Tuesday 10 November, Tuesday 17 November to Wednesday 25 November, crew 3, no note.
  Constraints:
  Waits on unfinished work: A104 is in progress and its scheduled finish, Wednesday 11 November, is before the check date. Its reported finish, Friday 13 November, is before A109's scheduled start, Tuesday 17 November, so only the first test applies.
  Overlap: O3, with A105.
  Delivery: D03, shipped, promised Monday 16 November, needed Tuesday 17 November. On time as promised, not counted.
  RFI: RFI-017, open, needed by Monday 16 November, due in the window.

WEEK 2: Thursday 19 November to Wednesday 25 November

A103 Level 2 east drywall hang. Drywall A, Level 2 east. Scheduled Monday 23 November to Wednesday 2 December. Status: not started. Waits on: A101; A102.
  Trade update: Tuesday 10 November, Monday 23 November to Wednesday 2 December, crew 6, no note.
  Constraints:
  Overlap: O4, with A108.

WEEK 3: Thursday 26 November to Wednesday 2 December

A107 Roof unit set. Mechanical A, Roof. Scheduled Monday 30 November to Tuesday 1 December. Status: not started. Waits on: nothing.
  Trade update: Monday 9 November, Monday 30 November to Tuesday 1 December, crew 2, note: "Crane booked for 30 November".
  Constraints:
  Delivery: D02, confirmed, promised Friday 27 November, which is a closed day. Needed Monday 30 November.
  RFI: RFI-019, open, needed by Monday 14 December. Needed after the activity starts (Monday 30 November).

A108 Level 2 east ceiling grid. Ceiling A, Level 2 east. Scheduled Monday 30 November to Wednesday 2 December. Status: not started. Waits on: A103.
  Trade update: none on file.
  Constraints:
  Waits on unfinished work: A103 is not started. Its later finish, Wednesday 2 December (scheduled and reported alike), is after A108's scheduled start, Monday 30 November.
  Trade update: no trade update on file.
  Overlap: O4, with A103.
  Approval: S02, submitted, with the reviewer 8 working days, needed by Wednesday 18 November; S04, submitted, with the reviewer 7 working days, needed by Friday 20 November.
  Delivery: D04, no promised date; status ordered, so the supplier has not confirmed.
  RFI: RFI-018, open, needed by Wednesday 25 November, due in the window.

TRADE OVERLAPS

O1 A101 (Mechanical A) and A102 (Electrical A), Level 2 east. Scheduled overlap: Thursday 12 November to Tuesday 17 November, 4 working days. On reported dates: Thursday 12 November to Thursday 19 November, 6 working days. Access: shared access (X3, X4).
O2 A104 (Framing A) and A105 (Electrical A), Level 3 west. Scheduled overlap: none, 0 working days. On reported dates: Thursday 12 November to Friday 13 November, 2 working days. Access: no access claim on file for A104.
O3 A105 (Electrical A) and A109 (Mechanical A), Level 3 west. Scheduled overlap: Tuesday 17 November to Tuesday 24 November, 6 working days. Access: access conflict (X1, X2; both exclusive).
O4 A103 (Drywall A) and A108 (Ceiling A), Level 2 east. Scheduled overlap: Monday 30 November to Wednesday 2 December, 3 working days. Access: access conflict (X5, X6; both exclusive).

OPEN APPROVALS AND SUBMITTALS

S01 Storefront glazing shop drawings (submittal), for A106. Status: revise and resubmit. Needed by Friday 6 November. Back with the submitter; overdue by 4 working days. Assigned to: ______
S03 Level 3 west electrical permit amendment (permit), for A105. Status: not submitted. Needed by Wednesday 11 November. Nothing has gone to the reviewer; overdue by 1 working day. Assigned to: ______
S02 Ceiling grid product data (submittal), for A108. Status: submitted Monday 2 November. Needed by Wednesday 18 November. With the reviewer 8 working days. Assigned to: ______
S04 Corridor ceiling finish (owner decision), for A108. Status: submitted Tuesday 3 November. Needed by Friday 20 November. With the reviewer 7 working days. Assigned to: ______
Clear and not listed: none.

DELIVERIES

D01 Storefront glazing units, for A106, Supplier A. Needed Monday 16 November. Promised Tuesday 24 November. Status: confirmed. Promised after the date needed, 6 working days late. Assigned to: ______
D03 Level 3 duct sections, for A109, Supplier C. Needed Tuesday 17 November. Promised Monday 16 November. Status: shipped. On time as promised, not counted.
D02 Rooftop unit, for A107, Supplier B. Needed Monday 30 November. Promised Friday 27 November. Status: confirmed. Promised for a closed day. Assigned to: ______
D04 Ceiling grid and tile, for A108, Supplier D. Needed Monday 30 November. Promised none. Status: ordered. No promised date; status ordered, so the supplier has not confirmed. Assigned to: ______
Clear and not listed: D05.

RFIS

RFI-014 Wall type at grid C, for A104. Issued Wednesday 28 October. Needed by Friday 6 November. Overdue by 4 working days. Assigned to: ______
RFI-017 Duct conflict at beam, for A109. Issued Thursday 5 November. Needed by Monday 16 November. Due in the window. Assigned to: ______
RFI-018 Corridor ceiling height, for A108. Issued Monday 9 November. Needed by Wednesday 25 November. Due in the window. Assigned to: ______
RFI-019 Roof curb dimension, for A107. Issued Tuesday 10 November. Needed by Monday 14 December. Needed after the activity starts. Assigned to: ______
Clear and not listed: RFI-011.

QUESTIONS FOR THE SUPERINTENDENT

1. A104, Level 3 west framing. The scheduled finish, Wednesday 11 November, has passed and the activity is in progress. Framing A reports finish Friday 13 November, 2 working days later, with a note that two walls are on hold for RFI-014, which is 4 working days overdue. A105 and A109 wait on it. Is Friday 13 November accepted for sequencing, and which trade lead confirms Framing A's capacity?
2. A101, Level 2 east ceiling duct rough-in. Mechanical A reports finish Thursday 19 November, 2 working days after the scheduled Tuesday 17 November, with a crew of 4 and no second shift. A103 waits on it. Does that change the sequencing, and which trade lead confirms Mechanical A's finish?
3. A105, Level 3 west electrical rough-in. It is scheduled to start today, Thursday 12 November, and waits on A104, which has not finished (scheduled finish passed; reported finish Friday 13 November). There is no trade update, so its duration is not confirmed by the trade, and permit amendment S03 has not been submitted. Nothing is listed as waiting on A105. Does A105 start on Thursday 12 November, and which trade lead confirms Electrical A's start and duration?
4. A106, Ground floor storefront glazing install. The latest update from Glazing A is from Monday 2 November, 10 days before the check date. Delivery D01 is promised 6 working days after it is needed, and S01 is back with the submitter, 4 working days overdue. Nothing is listed as waiting on A106. Does the start on Monday 16 November hold, and which trade lead confirms Glazing A's dates?
5. A109, Level 3 west duct rough-in. It waits on A104, which has not finished; the reported finish, Friday 13 November, is before A109's start on Tuesday 17 November. RFI-017 is open and needed by Monday 16 November. Nothing is listed as waiting on A109. Does A109 start on Tuesday 17 November, and which trade lead confirms Mechanical A's capacity?
6. A108, Level 2 east ceiling grid. It is scheduled to start Monday 30 November, but A103, which it waits on, finishes Wednesday 2 December. There is no trade update. Delivery D04 has no promised date, and S02, S04 and RFI-018 are open. A111, outside the window, waits on A108. What is the sequence between A103 and A108, and which trade lead confirms Ceiling A's dates?
7. O1, Level 2 east: A101 and A102. The two trades share the area for 4 working days as scheduled and 6 as reported. Both claims are shared (X3, X4). A103 waits on both. Do Mechanical A and Electrical A confirm they can work in the area together, and which trade leads confirm capacity?
8. O2, Level 3 west: A104 and A105. The scheduled dates do not overlap, but the reported dates share Thursday 12 November and Friday 13 November, 2 working days. No access claim is on file for A104. A105 and A109 wait on A104. Does A105 wait until A104 finishes, and which trade leads confirm capacity?
9. O3, Level 3 west: A105 and A109. The two trades overlap for 6 working days and both hold exclusive claims (X1, X2): an access conflict. Nothing is listed as waiting on either. Which plan for the area stands for those days, and which trade leads confirm capacity?
10. O4, Level 2 east: A103 and A108. The two trades overlap for 3 working days and both hold exclusive claims (X5, X6): an access conflict. A108 waits on A103 (question 6), and A111 waits on A108. Which plan for the area stands for those days, and which trade leads confirm capacity?

APPROVED AS NOTED

S05 Drywall board product data, for A103, Wednesday 28 October. The notes are on the approval itself.

NOTES THE REVIEW DOES NOT JUDGE

None.

LEFT OUT

A100 Level 2 east layout and marking: complete. Rows linked to left-out activities: 0.
A111 Level 2 east flooring: starts Monday 7 December, after the window ends. Rows linked to left-out activities: 1.

SUPPLIED BUT NOT LINKED

Delivery D06: fire-rated door frames, needed Friday 20 November, status not ordered. No activity named.
Trade update U09: Plumbing A, reported Tuesday 10 November, Wednesday 18 November to Friday 20 November, crew 2. Activity A120 is not on the schedule.

DECISION OF THE SUPERINTENDENT (left blank for them)
Sequencing: [ ] confirmed as listed   [ ] changed (note which activities)
Follow-up assigned on the lists above: [ ] yes   [ ] not yet
Capacity confirmed by the trade leads: [ ] yes   [ ] not yet
Name, role and date: ____________

Prepared for the Superintendent's meeting. No schedule has been changed, nothing has been sent, and no trade, supplier, designer or reviewer has been contacted.

## What was observed

**Every required part was produced.** The header, the five activity groups, the overlaps, the three follow-up lists, the questions, approved as noted, notes not judged, left out, supplied but not linked, the blank decision block and the closing line all came out in the template's order. Nothing made the run stop: the settings were complete, headings matched, no id was repeated, no date was ambiguous and no secret was in the files. The template's acceptance tests were not run; this was one run on the example only.

**Agreement with the published example.** After the run, the output was compared with the example's published output. The findings, the working-day counts, the overlap numbering, the follow-up lists, the header counts and the question order agree throughout. That includes the less obvious ones: the superseded update U08 is not used and is counted once; A104 is flagged as 1 working day past its finish and 2 working days later on the trade's report; the stale update on A106 is 10 days old; A105's constraint on A104 satisfies both of the predecessor tests; S02 and S04 are 8 and 7 working days with the reviewer; D02 is flagged for a closed day; RFI-019 is flagged as needed after the activity starts; D03 is shown as on time and not counted; and O2 appears with a scheduled count of zero.

**Differences from the example, all small:**

- The access line for O3 and O4. The example gives each claim's dates in the line; this run named the claims and said both are exclusive.
- Questions 7 to 10. This run named what waits on each of the two activities (for example, that A103 waits on both A101 and A102). The example does not.
- The "Approved as noted" line. This run printed the date 28 October (the date the item was submitted). The example prints no date.
- The "Left out" lines. This run gave "Rows linked to left-out activities" for each activity (0 and 1); the example gives one total of 1.
- Wording of the questions. The example asks sharper closing questions in places (for example, "Does A103 still start on Monday 23 November?" in question 2). This run asked the general question instead.
- This run added "no note" to trade updates with an empty note, and spelled out "Both tests apply" on A105.

**Facts not in the inputs.** None was found in this run. None was found in the example either, after checking each date, count and id in it against the inputs. The weekday names are derived from the dates and were checked against the calendar.

**Where the instructions were ambiguous and a guess was needed:**

1. *Both predecessor tests at once.* The template says to "say which of the two applies". For A105 both apply (the predecessor's scheduled finish has passed, and its later finish is after A105's start). This run said both. The template should say so.
2. *"What waits on the activity" for an overlap question.* An overlap involves two activities. The template does not say whether to name what waits on both, either, or the first. This run named both.
3. *Whether an overlap counts as a "constraint".* The header count "Activities with a constraint" is 9 only if an overlap, including a shared-access overlap, counts. The template does not say.
4. *The date on "Approved as noted".* The output format shows "[date]" without saying which date. This run used the submitted date.
5. *Rows linked to left-out activities.* The format prints the count at the end of each left-out line, but the example prints one total. This run printed one per line.
6. *Notes the review does not judge.* The template asks for notes that mention a safety hazard, a structural concern or a code or inspection requirement. Four records come close without stating one: "Duct conflict at beam" (RFI-017), "Fire-rated door frames" (D06), the permit amendment (S03) and "Corridor ceiling height" (RFI-018). This run treated none as a stated concern and printed "None." Another run could reasonably copy some of them. The template gives no test for the boundary.
7. *A date promised for a non-working weekday.* The delivery rule covers a promised date that is a closed day, but not a Saturday or Sunday. The example does not exercise it.
8. *Date style.* The format says "weekday date" and the template does not say whether the year is written. This run left the year out in the body and kept it in the header.
9. *Closed-day wording in the access conflict.* Whether the access finding must repeat each claim's dates is not stated.

**Shortcomings of the trial itself.** It is one run, by one model, that read the inputs and computed the counts by hand against a calendar built in the reasoning, with no code. It tested no stop condition, no refusal and no missing register. The result is that the template, as written, can be followed to a brief that agrees with its published example.

## Edits made after this run

After an independent review, small edits were made to the template and the example. They have not been run again, and nothing above has been changed. They are: both predecessor tests said to be reported together when both apply; the header count of activities with a constraint defined to include overlaps; the date on the approved-as-noted line defined as the date submitted; a test added for which notes are copied as not judged; promised dates on any non-working day covered by the delivery rule; the year shown only in the header; "due in the window" defined; every question to say what waits on the activity or that nothing does; the rows linked to left-out activities printed once as a total; and the example's wording, trade-update line and layout brought into line with the format.

A second round of small edits followed a further independent review. These have not been run again either, and nothing above has been changed. The access finding is now written with each claim's id, "exclusive" and its dates for an access conflict, and with the claim ids for shared access, which settles ambiguity 9 and matches the example (this run printed ids only). A line with no promised date now reads "Promised: none." Only working days on or after the check date count toward an overlap. The "Already under way or past its finish" group is stated to hold a not-started activity whose start has passed. The instruction block now also states the stop on an unrecognised status, the count of days with the reviewer, and the condition for "needed after the activity starts". The example's question 8 now says that nothing waits on A105. A rerun on the example would make this record stronger and has not been done.
