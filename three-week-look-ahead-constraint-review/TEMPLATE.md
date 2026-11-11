# Three-week look-ahead constraint review

Capability template, version 0.1.0.

## Purpose

Prepare the look-ahead brief a superintendent takes into the next coordination meeting. Every activity in the next three weeks of the approved schedule is set beside what could hold it up: work it waits on that is not finished, dates a trade reports that differ from the schedule, trades working in the same area, approvals and submittals still open, deliveries that are late, unpromised or unconfirmed, and RFIs without an answer. Each finding states the facts and the record it came from. The superintendent then confirms the sequencing and assigns the follow-up, and trade leads confirm their own capacity. The assistant prepares; it never changes the schedule, moves an activity, contacts a trade or supplier, answers an RFI, approves a submittal or decides whether work can proceed.

## When to use it and when not to

Use it two or three working days before a coordination meeting, once the trades have sent their latest dates. Run it again on the morning of the meeting if an update or a log has changed.

Do not use it:

- to recover a schedule that has already slipped. Comparing ways back to a committed date is a separate capability, schedule recovery options;
- to report progress to the owner or sponsor. That is a project status report;
- to compare supplier promise dates across every open purchase order. That is supplier delivery date check; this capability reads only the deliveries linked to activities in the window;
- to build or update the schedule itself. The project's scheduler owns the schedule;
- to judge whether a sequence is safe, whether a design works or whether work may proceed. Those are decisions for qualified site staff, the designers and the people accountable for safety;
- to decide who is owed time or money for a delay. That question goes to the contract team.

## Roles

- **Runs it:** the project engineer, project coordinator or field administrator who keeps the logs, or the superintendent.
- **Confirms sequencing and assigns every follow-up:** the superintendent.
- **Confirms capacity and dates for each trade:** the trade leads.
- **Answers RFIs and reviews submittals:** the designers, the owner's representatives and the reviewers named in the logs. Always people.
- **Keeps the schedule:** the project's scheduler or project controls.
- **Receives the brief:** supervision, trade partners, procurement and project controls, once the superintendent has approved it.

## Inputs

The person supplies these as files or pasted tables. The assistant needs no connection to any system and never asks for a password, a login code or any other secret.

1. **Settings.** The project name; the superintendent's role; the role that prepares the brief; the check date (today); the meeting date; the length of the window in weeks, three unless told otherwise; the working days of the week; the days the site is closed inside the window. If the project, the check date or the working days are missing, stop and ask. If the meeting date is missing, write "not stated".
2. **Schedule extract.** Default headings: `activity_id, activity, trade, location, start, finish, predecessors, status`. Status is not started, in progress or complete. Predecessors are activity ids separated by semicolons, or a dash for none. Dates are year-month-day. If there is no schedule, stop.
3. **Trade updates.** Default headings: `update_id, activity_id, trade, reported_on, reported_start, reported_finish, crew, note`. One row is what a trade said on one day. If not supplied, write "not supplied" and continue.
4. **Deliveries.** Default headings: `delivery_id, item, activity_id, supplier, needed_on, promised_on, status`. Status is not ordered, ordered, confirmed, shipped or delivered. Ordered means the supplier has not confirmed. If not supplied, write "not supplied" and continue.
5. **RFI log.** Default headings: `rfi_id, subject, activity_id, issued_on, needed_by, status, answered_on`. Status is open or answered. If not supplied, write "not supplied" and continue.
6. **Approvals and submittals log.** Default headings: `item_id, item, kind, activity_id, submitted_on, needed_by, status`. Kind is submittal, permit or owner decision. Status is not submitted, submitted, approved, approved as noted, revise and resubmit or rejected. If not supplied, write "not supplied" and continue.
7. **Access claims.** Default headings: `claim_id, area, trade, activity_id, from, to, exclusive`. Exclusive is yes when the trade needs the area to itself, no when it can share. If not supplied, write "not supplied" and continue.

If a file's headings do not match the defaults, in any order, stop and ask which column is which. Never guess a column. If a date is written in a way that could be read two ways, stop and ask.

## The procedure

1. **Check the inputs.** Confirm the settings. Confirm each file's headings. Count the rows in each. If two rows in one file share an id, stop and ask. If an activity's status is not one of the three, stop and ask. If a finish date comes before its start date, stop and ask which is wrong.
2. **Look for secrets.** If any file holds a password, a login code, a key or a similar secret, stop. Do not repeat it. Ask for the file again without it, and tell the person to let the system's owner know it was written down.
3. **Build the calendar.** The window runs from the check date for the number of weeks set, ending on the day before the same weekday that many weeks later. Week 1 is the first seven days of the window, week 2 the next seven, and so on. A working day is a day of a working weekday that is not a closed day. Every count of days in this procedure is in working days. A weekday date is written as the weekday, day and month (Thursday 12 November); the year appears only in the header's check date, window and closed days, or where a date falls in a different year from the check date. "Working days after A up to and including B" means the working days that fall after date A, ending on B itself.
4. **Choose the activities.** An activity is in the window when its status is not complete and its scheduled start is on or before the last day of the window. An activity that is complete, or that starts after the window ends, is left out and listed with its reason. An in-window activity whose scheduled start is before the check date goes in the group "Already under way or past its finish"; each other activity goes in the week of its scheduled start. That group also holds a not-started activity whose scheduled start has passed; the heading is kept as it is. Within a group, order by scheduled start, then by id.
5. **Link every row.** Each register row answers the activity its `activity_id` names. A row with a blank activity, or an activity not on the schedule, is never dropped: it goes under "Supplied but not linked". A row linked to an activity that was left out is counted, not listed; the count is printed once, as one total, under Left out.
6. **Use only the latest update.** For each activity, the latest trade update is the row with the latest `reported_on`. Earlier rows are superseded: count them, do not use them. The dates "as reported" are that row's reported start and finish.
7. **Find the constraints on each in-window activity.** Apply every rule below, and write each finding as facts with the record id. Change nothing and move nothing.
   - **Waits on unfinished work.** For each predecessor on the schedule: flag it if it is not complete and either (a) its scheduled finish is before the check date, or (b) the later of its scheduled finish and its reported finish falls after this activity's scheduled start. Say which test applies, or that both do, and give the predecessor's status and both finish dates. A predecessor id that is not on the schedule is flagged as unknown.
   - **Dates.** Flag an in-window activity that is not complete and whose scheduled finish is before the check date: it is past its scheduled finish, and the finding gives how many working days past. Flag an activity not started whose scheduled start is before the check date. Where there is a latest update, flag any difference between its reported start or finish and the scheduled one, giving the difference in working days and whether the trade reports later or earlier. Show the trade's note as written; draw no conclusion from it.
   - **Trade update.** Flag an activity with no trade update ("no trade update on file") and one whose latest update is more than [7] calendar days before the check date ("stale update"). Both mean the duration is not confirmed by the trade.
   - **Overlap.** Two in-window activities with the same location (matched on the text, ignoring capitals) and different trades overlap when they share at least one working day. Test the scheduled dates; then test each activity's reported dates where it has a latest update and its scheduled dates where it has none. Count only working days from the check date on; a shared day before the check date is not counted. List the pair if either test gives one working day or more, and give both counts when they differ. A pair with the same trade is not listed. Then look in the access claims: if both activities have a claim and both claims are exclusive and the claims overlap by a working day, write "access conflict" and name each claim with its id, "exclusive" and its from and to dates; if both claims are shared, write "shared access" and name the claim ids; if either activity has no claim, write "no access claim on file for [id]".
   - **Approval.** A log item linked to the activity is open unless its status is approved or approved as noted. Overdue means needed_by is before the check date; say by how many working days. For a submitted item, give the working days it has been with the reviewer, counted from the day after submitted_on to the check date. Revise and resubmit or rejected means the item is back with the submitter, not the reviewer. Not submitted means nothing has gone to the reviewer. If needed_by is after the activity's scheduled start and the activity has not started, flag "needed after the activity starts". Approved as noted items are not open; list them separately.
   - **Delivery.** A delivery linked to the activity is clear when delivered. Otherwise list every reason that applies, in this order: not ordered; no promised date; promised after the date needed, with the working days late; promised for a day that is not a working day (a closed day, or a day of a non-working weekday); status ordered, so the supplier has not confirmed. A delivery with none of these reasons is "on time as promised": show it, but it is not counted as an item to chase.
   - **RFI.** An RFI linked to the activity is open unless answered. If needed_by is before the check date, it is overdue by that many working days. An open RFI is "due in the window" when its needed_by is on or after the check date and on or before the activity's scheduled start, or, for an activity already under way, on or after the check date. If it has no needed_by, flag that. If needed_by is after the activity's scheduled start and the activity has not started, flag "needed after the activity starts".
8. **List the overlaps.** Number the pairs from step 7 in the order of the first working day they share (by the scheduled test, else the reported one), then by the lower activity id. Give for each the activities, trades, location, the shared days and their count, and the access finding.
9. **Write the follow-up lists.** Open approvals, deliveries to chase and open RFIs each become a list in the order of the date needed (needed_by or needed_on), then by id, each item with "Assigned to:" left blank. A delivery on time as promised is shown in the delivery list without a blank. Items that are clear (delivered deliveries, answered RFIs, approved approvals) are not listed; their ids are printed on a "Clear and not listed" line so that nothing supplied goes unaccounted for. The assistant assigns no one.
10. **Write the questions.** Number them for the superintendent. First, one question for each activity that has a "waits on", "dates" or "trade update" finding, in the order the activities are printed. Then one question for each overlap. Each question gives the facts, names what waits on the activity (the activities that list it as a predecessor, including any outside the window), or says "Nothing waits on it.", and asks what the superintendent must settle, including which trade lead confirms capacity. A question about an overlap names what waits on each of its two activities, or says that nothing waits on them. Recommend nothing unless the person asks.
11. **Notes that are not judged.** If the words of any trade note, log entry or subject themselves state or report a safety hazard, a structural concern or a code or inspection requirement, copy the words as written under "Notes the review does not judge", with the record id. A subject that only names a building element, a system or a rating ("Duct conflict at beam", "Fire-rated door frames") states nothing and is not copied. Do not comment on any of them.
12. **Count and return.** Print the counts in the header from the lists. An activity has a constraint when it has at least one finding of any kind, an overlap (shared access included) among them. Return the brief to the person who ran it, for the superintendent's approval. The superintendent confirms sequencing, assigns follow-up, and shares the approved brief; the trade leads confirm capacity.

## Exceptions and stop conditions

- **No schedule, no check date or no working days:** stop and ask.
- **Headings that do not match the defaults, an id used twice, an unreadable date, or a finish before its start:** stop and ask.
- **A register not supplied:** continue, name it in the header, and say which checks were not made.
- **Durations or dates the trade has not confirmed:** report them as unverified, as in the trade update rule. Do not substitute a duration of your own.
- **Two plans for the same area that conflict:** report them as an access conflict and put the question to the superintendent. Do not choose between them.
- **Asked to change a date, move an activity, resequence the work or add an activity:** decline and name the role that does it, the scheduler or the superintendent.
- **Asked whether the work is safe, whether a design or sequence is sound, or what an inspection requires:** decline. The people accountable for safety and design decide; copy any note on the subject under "Notes the review does not judge".
- **Asked who is entitled to time or money, or to write to a trade or supplier about it:** decline and refer it to the contract team.
- **Asked to contact a trade, supplier, designer or reviewer, answer an RFI or approve a submittal:** decline. The follow-up lists are for the superintendent to assign.
- **Asked to compare ways to recover lost time:** decline and point to the separate recovery capability.
- **The files contain a password, a login code or a key:** do not repeat it; tell the person to remove it.

## Output format

```
THREE-WEEK LOOK-AHEAD CONSTRAINT REVIEW: [project]

For: [superintendent role]. Prepared by: [role]. Check date: [weekday date]. Meeting: [weekday date / not stated].
Window: [weekday date] to [weekday date] ([n] weeks). Working days: [days of the week]. Closed days in the window: [dates / none].
Supplied: schedule ([n] activities); trade updates ([n] rows, [n] superseded); deliveries ([n] rows); RFIs ([n] rows); approvals ([n] rows); access claims ([n] rows).
Not supplied: [registers / none]. Checks not made because of it: [list / none].
Activities in the window: [n]. Left out: [n]. Activities with a constraint: [n].
Items to chase: approvals [n], deliveries [n], RFIs [n].

ALREADY UNDER WAY OR PAST ITS FINISH
WEEK 1: [weekday date] to [weekday date]
WEEK 2: [weekday date] to [weekday date]
WEEK 3: [weekday date] to [weekday date]
(Each group lists its activities in this form, or "No activity here." when it has none.)
[id] [activity]. [Trade], [location]. Scheduled [weekday date] to [weekday date]. Status: [status]. Waits on: [ids / nothing].
  Trade update: [reported_on, reported start to finish, crew, note as written / none on file / stale: reported_on, ...]
  Constraints: [none found / one line each, using these labels:]
  Waits on unfinished work: [facts]
  Dates: [facts]
  Trade update: [no trade update on file / stale update, n days before the check date]
  Overlap: [O number, with the other activity]
  Approval: [id, status, facts]
  Delivery: [id, reasons]
  RFI: [id, status, facts]

TRADE OVERLAPS
O[n] [activity and trade] and [activity and trade], [location]. Scheduled overlap: [first day] to [last day], [n] working days. On reported dates: [first day] to [last day], [n] working days. Access: [access conflict (each claim: id, exclusive, from date to last date) / shared access (claim ids) / no access claim on file for ...]
(Print "None." if there are no overlaps. Omit the "On reported dates" sentence when the count is the same.)

OPEN APPROVALS AND SUBMITTALS
[id] [item] ([kind]), for [activity id]. Status: [status]. Needed by [weekday date]. [Facts.] Assigned to: ______
Clear and not listed: [ids / none]
(Print "None." under the heading if there are no open items.)

DELIVERIES
[id] [item], for [activity id], [supplier]. Needed [weekday date]. [Promised [weekday date]. / Promised: none.] Status: [status]. [Reasons / On time as promised, not counted.] [Assigned to: ______ for every item counted]
Clear and not listed: [ids / none]
(Print "None." under the heading if there are no deliveries to show.)

RFIS
[id] [subject], for [activity id]. Issued [weekday date]. Needed by [weekday date / not stated]. [Overdue by n working days / due in the window / flag.] Assigned to: ______
Clear and not listed: [ids / none]
(Print "None." under the heading if there are no open RFIs.)

QUESTIONS FOR THE [superintendent role]
[n]. [Activity or overlap]. [Facts.] [What waits on it.] [The question.]
(Print "None." if there are none.)

APPROVED AS NOTED
[id] [item], for [activity id], submitted [weekday date]. The notes are on the approval itself. (Print "None." if there are none.)

NOTES THE REVIEW DOES NOT JUDGE
[record id]: "[words as written]". (Print "None." if there are none.)

LEFT OUT
[id] [activity]: [complete / starts [weekday date], after the window ends].
Rows linked to left-out activities: [n].

SUPPLIED BUT NOT LINKED
[register] [id]: [what it says]. [Why: no activity named / activity not on the schedule.] (Print "None." if there are none.)

DECISION OF THE [superintendent role] (left blank for them)
Sequencing: [ ] confirmed as listed   [ ] changed (note which activities)
Follow-up assigned on the lists above: [ ] yes   [ ] not yet
Capacity confirmed by the trade leads: [ ] yes   [ ] not yet
Name, role and date: ____________

Prepared for the [superintendent role]'s meeting. No schedule has been changed, nothing has been sent, and no trade, supplier, designer or reviewer has been contacted.
```

## Reviewer checklist

1. The window starts on the check date, covers the weeks set, and every date has the right weekday. (Superintendent)
2. Every activity that is not complete and starts inside the window is printed once, in the right group; every left-out activity has its reason. (Project coordinator)
3. Each activity's scheduled dates, trade and predecessors match the schedule extract exactly. (Project coordinator)
4. Each trade update shown is the latest for its activity, and each difference in days is counted in working days with the closed days skipped. (Project coordinator)
5. Every overlap is a pair in the same location with different trades, and the shared working days are counted correctly on both tests. (Superintendent)
6. Every approval, delivery and RFI finding agrees with its log row, and every overdue count is right. (Project coordinator)
7. Each item to chase appears once in its list with "Assigned to" blank, and the header counts match the lists. (Project coordinator)
8. Each question states facts that trace to a record, names what waits on the activity, and recommends nothing. (Superintendent)
9. The brief changes no date, assigns no one, and gives no view on safety, design or entitlement. (Superintendent)
10. The superintendent has confirmed the sequencing and the trade leads have confirmed capacity before the brief is shared. (Superintendent)

## Acceptance tests

Proposed tests. None has been run.

1. **Clean week.** Every activity has a current update that matches the schedule, no overlaps, and every log item is clear. Expected: "Constraints: none found" on each activity, "None." in each list, zero counts.
2. **Predecessor past its finish.** A predecessor has status in progress and a scheduled finish before the check date. Expected: its successors flagged, with the predecessor's scheduled and reported finish.
3. **Schedule that starts a successor before its predecessor ends.** Expected: flagged under waits on unfinished work, using the scheduled dates; nothing moved.
4. **Closed days.** A closed day falls inside a delivery's lateness and inside an overlap. Expected: it is skipped in every count.
5. **Stale and missing updates.** One activity with no update, one with an update eight days old. Expected: both reported as not confirmed by the trade, with the day count for the stale one.
6. **Superseded update.** Two updates for one activity with different dates. Expected: the later one used, the earlier counted as superseded.
7. **Overlap on reported dates only.** The scheduled dates do not overlap but the reported dates do. Expected: listed, with a scheduled count of zero.
8. **Two exclusive claims in one area.** Expected: an access conflict naming both claims, a question, and no choice between them.
9. **RFI needed after the activity starts.** Expected: flagged for the activity, not treated as overdue.
10. **Delivery promised for a closed day, and one with no promised date.** Expected: each flagged for its own reason; a delivery that is shipped and promised before it is needed shown as on time and not counted.
11. **Approved as noted.** Expected: listed under approved as noted, not as open.
12. **Row with no activity, and a row for an unknown activity.** Expected: both under "Supplied but not linked".
13. **A renamed column.** Expected: stops and asks which column is which.
14. **Asked to move an activity, answer an RFI, contact a supplier or say whether the sequence is safe.** Expected: declines each, names the role that decides, and offers the follow-up list instead.
15. **A trade note that mentions a hazard.** Expected: copied as written under "Notes the review does not judge", with no comment.

## Instructions for the AI assistant

Paste this block as custom instructions, followed by the output format above.

```
You prepare a three-week look-ahead constraint review for a superintendent
from the project's own records. You prepare; people decide. You never
change a date, move or add an activity, contact a trade, supplier,
designer or reviewer, answer an RFI, approve a submittal, assign
follow-up, send anything or change any record. You make no safety,
design or engineering call and no view on who is owed time or money. You
never ask for a password or a login code and need no access to any system.

The user will supply: the settings (project, superintendent's role, who
prepares it, check date, meeting date, weeks in the window, working
weekdays, closed days); the schedule extract (activity_id, activity,
trade, location, start, finish, predecessors, status); trade updates
(update_id, activity_id, trade, reported_on, reported_start,
reported_finish, crew, note); deliveries (delivery_id, item,
activity_id, supplier, needed_on, promised_on, status); the RFI log
(rfi_id, subject, activity_id, issued_on, needed_by, status,
answered_on); the approvals log (item_id, item, kind, activity_id,
submitted_on, needed_by, status); and access claims (claim_id, area,
trade, activity_id, from, to, exclusive). If the schedule, the project,
the check date or the working days are missing, stop and ask. If a
heading does not match, an id is used twice, a date can be read two ways,
a finish comes before its start or an activity's status is not one of
not started, in progress or complete, stop and ask; never guess a column.
If another register is missing, say so in the header, say which checks
were not made, and continue. If a file holds a password or a key, do not
repeat it; tell the user to remove it.

1. The window runs from the check date for [3] weeks. Week 1 is the first
   seven days, week 2 the next seven, and so on. Count every number of
   days in working days, skipping non-working weekdays and closed days.
   "Working days after A up to and including B" excludes A and includes B.
   Write a weekday date as the weekday, day and month; give the year only
   in the header and for a date outside the check date's year.
2. Include each activity that is not complete and starts on or before the
   last day of the window. Put those that start before the check date in
   "Already under way or past its finish"; put the others in the week of
   their scheduled start. That first group also holds a not-started
   activity whose scheduled start has passed. Order by scheduled start,
   then id. List the
   others under Left out with the reason.
3. A row with no activity, or one the schedule does not hold, goes under
   "Supplied but not linked". A row for a left-out activity is counted
   only, as one total under Left out. Use only the latest trade update
   for each activity (latest reported_on); count the earlier ones as
   superseded.
4. For each in-window activity, test and report as facts with record ids:
   - Waits on unfinished work: a predecessor that is not complete and
     either (a) has a scheduled finish before the check date or (b) has a
     later finish (scheduled or reported) after this activity's scheduled
     start. Say which test applies, or that both do. A predecessor not on
     the schedule is unknown.
   - Dates: not complete and past its scheduled finish (working days
     past); not started and past its scheduled start; any difference
     between reported and scheduled dates in working days, later or
     earlier. Show the trade's note as written; infer nothing.
   - Trade update: none on file, or older than [7] calendar days before
     the check date. Both mean the duration is not confirmed. Print a
     stale update's line as "stale: reported_on, ...".
   - Overlap: same location (text match), different trades, at least one
     shared working day on or after the check date, on scheduled dates or
     on reported dates (reported where an update exists, scheduled
     otherwise). Give both counts when they differ. Then the access
     claims: both exclusive and overlapping is an access conflict, written
     with each claim's id, "exclusive" and its from and to dates; both
     shared is shared access, written with the claim ids; a missing claim
     is "no access claim on file for [id]".
   - Approval: open unless approved or approved as noted. Overdue when
     needed_by is before the check date (working days). For submitted,
     give the working days with the reviewer, counted from the day after
     submitted_on to the check date. Revise and resubmit or rejected is
     back with the submitter. Flag "needed after the activity starts"
     when needed_by is after the scheduled start of an activity not yet
     started. List approved as
     noted separately, with the date submitted.
   - Delivery: clear when delivered. Otherwise give every reason that
     applies in this order: not ordered; no promised date; promised
     after needed (working days late); promised for a day that is not a
     working day (closed day or non-working weekday); status
     ordered (supplier has not confirmed). None of these: "on time as
     promised", shown but not counted.
   - RFI: open unless answered; overdue by working days when needed_by is
     before the check date; "due in the window" when needed_by is on or
     after the check date and on or before the activity's scheduled start
     (for an activity already under way, on or after the check date);
     flag a missing needed_by; flag "needed after the activity starts"
     when needed_by is after the scheduled start of an activity not yet
     started.
5. Number the overlaps by their first shared working day, then by lower
   activity id. Write the approvals, deliveries and RFIs to chase in date
   order with "Assigned to:" blank. Never fill it in. Print the ids of
   clear items (delivered, answered, approved) on a "Clear and not
   listed" line under each list.
6. Write numbered questions for the superintendent: first one for each
   activity with a waits-on, dates or trade-update finding, in printed
   order; then one for each overlap. Give the facts, name what waits on
   the activity (activities listing it as a predecessor, including any
   outside the window) or say "Nothing waits on it."; for an overlap name
   what waits on each of its two activities. Ask what must be settled,
   including which trade lead confirms capacity. Recommend nothing unless
   asked.
7. If the words of a note, subject or log entry themselves state a
   safety hazard, a structural concern or a code or inspection
   requirement, copy them under "Notes the review does not judge" with
   the record id, and add no comment. A subject that only names an
   element, system or rating is not copied.
8. An activity has a constraint when it has any finding, an overlap
   included. Use the output format exactly. Print "None." for an empty
   list and "No activity here." for an empty group. Print the counts
   from the lists. End with the closing line that says no schedule has been
   changed, nothing sent and nobody contacted.

If asked to change or move a date or an activity, decline and name the
scheduler or the superintendent. If asked whether work is safe, whether
a design or sequence is sound, or what an inspection requires, decline
and refer it to the people accountable. If asked who is owed time or
money, or to write to a trade or supplier about it, decline and refer it
to the contract team. If asked to contact anyone, answer an RFI, approve
a submittal or assign follow-up, decline and point to the lists. If asked
for ways to recover lost time, decline and point to the separate recovery
capability. Check every date and every count against the calendar you
built before you return the brief.
```

## What to customize

- The length of the window. Three weeks is the default; some projects use two or four.
- The stale-update limit, seven days as written.
- The working days and the closed days you use for holidays and shutdowns.
- The columns of your schedule export. Map your scheduling product's headings to the defaults once, and keep the mapping with the template.
- The statuses your logs use for approvals and deliveries, and which of them count as clear.
- How you name locations. Overlaps are found by matching the text, so use one spelling for each area in the schedule and the access claims.
- Whether your project keeps access claims. Without them the review reports overlaps and says no claim is on file.
- The lists you want in the brief, such as permits, inspections or owner decisions, and the kind each belongs to.
- Who receives the approved brief and where the signed decision is kept.
- Which files the assistant may read in ChatGPT, Claude, Copilot or Gemini.

## Version notes

- 0.1.0, 10 November 2026. Written by Fully Powered AI from its own published map of the work. Editorially reviewed. Tried on its invented example on 10 November 2026 in one run (Claude); the record is published with it, and lists the small edits made afterward that have not been run again. Not yet tested in a client environment.
