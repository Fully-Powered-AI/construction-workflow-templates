# Punch list consolidation

Workflow template, version 0.1.0.

## Purpose

Prepare one consolidated punch list for the next closeout walk from three things the site manager already has: the prior punch list, the notes and photographs from the latest walk, and the updates trades have sent. The list is grouped by location and then trade, merges entries that plainly repeat each other, attaches the photograph references, prints each trade's note word for word, flags what is overdue or raised again, and proposes a date for the next check of each item that is not closed. The assistant prepares; it never assigns work, changes a status, closes an item, accepts work as complete, judges workmanship, certifies that anything is safe or compliant, contacts a trade, or changes a record. The site manager assigns the work, and the authorized inspector or owner representative accepts completion.

## When to use it and when not to

Use it after a closeout walk, once the notes are typed up and before the list goes to the trades. Run it again after the next walk and whenever updates arrive.

Do not use it:

- to decide whether work is acceptable. That is the authorized inspector's or owner representative's decision, and photographs alone do not establish it;
- to treat a trade's note that work is done as a closed item. Reported complete and verified closed are different statuses;
- to follow up on concerns about safety raised on a walk. That is safety walk follow-up, and it belongs with the project's safety professional;
- to check that manuals, warranties, as-builts and training are ready for turnover. That is project handover readiness check;
- to track submittals or orders. That is submittal register review.

## Roles

- **Runs it:** the site manager, or the site coordinator working for them.
- **Settles every question and assigns the work:** the site manager, or [your decider].
- **Verifies that work is complete and accepts it:** the authorized inspector or owner representative, as the project names them. Always a person.
- **Does the work and reports on it:** the trade named on each item.
- **Updates the punch list and sends it to the trades:** the people the project names, after the site manager decides.

## Inputs

The assistant works only from the files and notes the person supplies. It needs no connection to the project management system and never asks for a password or a login code. It reads photograph file names, not the pictures, and judges nothing from an image.

1. **The prior punch list.** One row per item. Default column headers: `item_no`, `location`, `trade`, `description`, `date_added`, `recorded_status`, `contractor_note`, `assigned_to`, `due_date`, `verified_by`, `verified_date`. `recorded_status` is exactly one of `open`, `contractor reports complete` or `verified closed` ([your status words]), or blank, which is read as `open`. A row recorded as `verified closed` needs `verified_by` and `verified_date`. A blank `due_date` is read as not supplied. An empty prior list is allowed for the first walk.
2. **The walk notes.** One row per observation. Default column headers: `note_no`, `walk_date`, `location`, `trade`, `observation`, `photo_ref`, `refers_to`. `photo_ref` is a file name and may be blank. `refers_to` is an item number from the prior list when the person already knows the note repeats that item, and may be blank. A blank `trade` is allowed.
3. **The contractor updates.** One row per update received. Default column headers: `update_no`, `item_no`, `location`, `trade`, `update_text`, `update_date`, `reports_complete`, `promised_date`, `photo_ref`. `reports_complete` is `yes` or `no`; blank is read as `no`. `item_no`, `promised_date` and `photo_ref` may be blank. No updates is allowed.
4. **The settings,** typed: the project, today's date, the walk date and who decides. Also the days to allow before an item is checked again (default 7, [your follow-up days]), the next walk date (optional) and the target closeout date (optional). Days are counted as calendar days. Each default used is named after "Defaults used" on the Settings line.

**Column check.** Before any other work, compare each file's headers with the defaults, or with the project's own headers if [your column headers] are set. If a header is missing or named differently, stop. List the headers expected and the headers found, ask which column is which, and prepare nothing else. Never guess a column.

## The procedure

1. **Check the inputs.** Run the column check. Confirm today's date and the walk date. A status that is not one of the allowed words, a date that is not a real date, a `reports_complete` that is neither yes nor no, two prior rows with the same `item_no`, or a `refers_to` or `item_no` that is not on the prior list: stop and ask.
2. **Check the data.** List under Data checks: an update with no item number and how it was handled (step 5); a walk note with no trade; a walk note or update with a location or trade written several ways (the names are not merged; say that they differ); a prior item with no due date, noting that none was invented (new items never have a due date, so this check and the line "No due date recorded" apply to prior items only); a `verified closed` row missing `verified_by` or `verified_date` (treat it as CONTRACTOR REPORTS COMPLETE and say so); and any walk note or update whose own words include "unsafe", "hazard" or "danger", quoted word for word with a line telling the site manager to take it through the project's safety process, outside this list. If there are none of the last kind, say so.
3. **Normalise for matching only.** Two pieces of text match when they are the same after ignoring case, extra spaces and punctuation. Print the text as it was written, using the first version seen.
4. **Merge walk notes into items.** A walk note joins an existing item when its `refers_to` names that item, or when its location, trade and observation all match the item's location, trade and description. A walk note that matches nothing becomes a new item, numbered NEW-1, NEW-2 and so on in note order; the site manager gives the real numbers. Never merge on similar meaning alone. Print the walk observation word for word, with the date, when it differs from the item's description. Show how each merge was made: "same text" or "the walk note names [item]". When a walk note matches both ways, print "the walk note names [item]".
5. **Attach the updates.** An update joins the item named in `item_no`. An update with no item number joins an item only when exactly one item that is not verified closed has the same location and trade; otherwise leave it unattached and list it under Data checks. Print the update text word for word in quotation marks with its date, and the promised date. An update never changes a status by itself, except that `reports_complete` of yes on an OPEN item gives the label in step 6.
6. **Set the status label,** exactly one per item: OPEN (recorded open or blank, or reported complete in the prior list and seen again at the walk); CONTRACTOR REPORTS COMPLETE, not verified (recorded as such, or an update with `reports_complete` yes on an open item, with no newer walk note on it); VERIFIED CLOSED with the verifier and date. A trade's note is never printed as closure. A walk note on a VERIFIED CLOSED item (by `refers_to` or a text match) leaves the label unchanged, marks the item "Raised again at the walk" and generates a question; the assistant never reopens it. A walk note on an item recorded as reported complete makes it OPEN and marks it "Raised again at the walk"; apply this step before step 9, so that item is then tested for overdue as an OPEN item. A walk note merged into an item that was already OPEN is not "raised again" and is not counted as such. This holds even when an update on that item reports complete and a walk note on it has the same date or a later one: the item stays OPEN, is not counted as "Raised again at the walk", and both are printed and the site manager is asked (see Exceptions).
7. **Mark the repeats that are not merged.** Two items that are not verified closed, in the same location, with the same trade, and different wording, are each marked "Possible duplicate of [number]". They are never merged. List each pair once, with both wordings in quotation marks.
8. **Attach the evidence.** For each item list every `photo_ref` from its merged walk notes, labelled "walk" with the walk date, and from its attached updates, labelled "contractor update" with the update date. A photograph reference is evidence that a picture exists, not that work is complete. An item with none says "No photograph supplied" and is listed under Items with no photograph.
9. **Check for overdue items.** An OPEN item with a `due_date` before today is overdue by today minus the due date, in days. Items reported complete or verified closed are not overdue.
10. **Propose follow-up dates,** for every item that is not VERIFIED CLOSED. Use the first that applies: (a) the latest `promised_date` from an attached update that is not before today (basis: trade's date); (b) the existing `due_date`, if it is not before today (basis: existing due date); (c) the next walk date, if supplied and not before today (basis: next walk); otherwise (d) the walk date plus the follow-up days (basis: default). For an item reported complete the date is a verification check, and the basis says so. Where the proposed date is later than the existing due date, say so with the number of days. If a proposed date is after the target closeout date, say so. A VERIFIED CLOSED item that was raised again gets "none until the site manager decides". In the Summary breakdown each date is counted once: a verification date is counted only under verification, even when it was found by the default rule. These are proposals; the site manager sets every date.
11. **Group and order.** Group by location in alphabetical order, with items that have no location last under "Location not stated". Within a location, group by trade in alphabetical order, with "Trade not stated" last. Within a trade, order by item number, prior items first, then new items.
12. **Write the questions,** numbered, in the order items appear by number (prior items first, then new items). Write one for each item that is overdue, raised again, reported complete, a possible duplicate (one question for the pair), without a stated trade, or whose proposed date is later than its existing due date. An item with several reasons shares one question. Each states the facts first (status, dates, the trade's words, the photograph) and then asks what the site manager wants done. A question recommends nothing and offers no wording for a message. Close the questions with one sentence saying that completion is accepted only by the authorized inspector or owner representative, that a trade's note of completion is not verified closure, and that assigning the work is the site manager's decision.
13. **Return the list** to the person who ran it, for [your decider]. A person updates the punch list, assigns the work and contacts the trades.

## Exceptions and stop conditions

- **A column header is missing or named differently:** stop; list expected and found headers; ask.
- **A status word that is not allowed, an invalid date, a duplicate item number, or an item number that is not on the prior list:** stop and ask.
- **A walk note and an update disagree about whether work is done:** print both as written and ask; never settle which stands.
- **A date that cannot be read, such as "next week":** treat it as not supplied and show the words.
- **A location or trade written several ways:** do not merge them. Show them as they are and mention under Data checks that the names differ, so the site manager can agree on one.
- **Asked whether work is acceptable or a defect is serious, to inspect or judge a photograph, to close or reopen an item, or to decide who is responsible:** decline and name the authorized inspector, the owner representative or the site manager.
- **Asked to send the list to a trade, assign work or change the punch list:** decline and name the role that does it.
- **The files contain a password, a login code or bank details:** do not repeat them; tell the person to remove them from the source.

## Output format

```
PUNCH LIST CONSOLIDATION: [project], walk of [weekday date]

For: [decider role]. Prepared [weekday date] from: prior punch list ([n] rows), walk notes ([n] rows), contractor updates ([n] rows), settings.
Column check: [all headers matched].
Settings: walk date [weekday date], follow-up [n] days, next walk [weekday date / not supplied], target closeout [weekday date / not supplied], counted in calendar days. Defaults used: [list / none].
Summary: [n] items. Open [n] (overdue [n]). Contractor reports complete, awaiting verification [n]. Verified closed [n]. Raised again at the walk [n]. Walk notes [n]: merged into existing items [n], new items [n]. Contractor updates attached [n]. Possible duplicates not merged [n] pairs. Items with no photograph [n]. Trade not stated [n]. Proposed follow-up dates [n] (trade's own date [n], existing due date [n], next walk [n], default [n], verification [n]); after target closeout [n].

Data checks
- [Each check, with what was done / None.]

Punch list

[Location]

[Trade]

- [Number] [description]. [STATUS LABEL][: verifier, weekday date]. [Overdue by [n] days (due [weekday date]) / Due [weekday date].] [Raised again at the walk, [weekday date]: "[observation]" / with the same wording.] Merged: [rows, with how matched]. [Earlier contractor note: "[words]".] [Update [number], [weekday date]: "[words]", promised [weekday date] / reports complete.] Evidence: [reference ([walk / contractor update], [weekday date]); ...] / No photograph supplied. [Possible duplicate of [number].] [No due date recorded.] Proposed follow-up: [weekday date] ([basis]) [, [n] days later than the existing due date] [, after the target closeout date] / none until the site manager decides.

Possible duplicates, not merged: [n] pairs
- [Number] and [number], [location], [trade]. Same location and trade, different wording: "[words]" and "[words]". / None.

Raised again at the walk: [n]
- [Number], [what was recorded before and when], seen again [weekday date]. [Label now shown.] / None.

Reported complete, awaiting verification: [n]
- [Number] [description] ([trade]): reported [weekday date][, with [reference]]. Proposed check [weekday date]. / None.

Overdue open items: [n]
- [Number] [description]: [n] days (due [weekday date]). / None.

Items with no photograph: [n]
- [Number] [description] ([location], [trade]). / None.

Questions for the [decider role]
1. [Number] [description] ([trade]). [Facts.] [Question.]
[Closing sentence on acceptance and assigning.]

Draft for the [decider role]'s decisions. No trade, inspector or owner representative has been contacted, and no punch list, status or due date has been changed.
```

Write [weekday date] like Tuesday 17 November 2026. Overdue items are listed longest first, then by number. Every thing the instructions require has a place above. Where a section has nothing in it, print "None." under its heading.

## Reviewer checklist

1. Every prior item appears once, with its status in the project's recorded words, and no trade's note is shown as closure. (Site manager)
2. Every merge is either an exact text match or a walk note that names the item, and nothing was merged on similar meaning. (Site coordinator)
3. Possible duplicates are listed and left separate. (Site manager)
4. Items are grouped by location then trade in the stated order, and the counts in the summary agree with the list. (Site coordinator)
5. Overdue days and proposed dates match a calendar, and each proposed date shows its basis. (Site manager)
6. Every photograph reference belongs to the item it is shown under, and items without one are listed. (Site coordinator)
7. Items raised again after verified closure were not reopened. (Authorized inspector or owner representative)
8. No sentence judges workmanship, safety or compliance, and nothing has been sent, assigned, closed or changed. (Site manager)

## Acceptance tests

Proposed tests. None has been run.

1. **First walk.** No prior list, a dozen walk notes, no updates. Expected: every item is NEW, grouped by location and trade, none overdue, default dates.
2. **Exact repeat.** A walk note matches an open item's location, trade and wording apart from case. Expected: merged, shown as "same text".
3. **Looks alike.** Two notes in the same place and trade describe one defect in different words. Expected: kept separate, marked as possible duplicates, one question.
4. **Note names the item.** A walk note with `refers_to` set to an open item. Expected: merged, shown as "the walk note names" the item.
5. **Trade says done.** An update with `reports_complete` yes on an open item. Expected: CONTRACTOR REPORTS COMPLETE, not verified; a verification date proposed; never closed.
6. **Seen again after reported complete.** A walk note on an item recorded as reported complete. Expected: OPEN, raised again, a question.
7. **Seen again after verified closure.** A walk note on a verified closed item. Expected: label unchanged, raised again, a question, no follow-up date.
8. **Overdue.** An open item due before today. Expected: overdue by the right number of days and listed.
9. **Update with no item number.** One matching item by location and trade, then two matching items. Expected: attached in the first case; unattached and listed under Data checks in the second.
10. **Proposed date after the closeout target.** Expected: the date is shown with a note that it falls after the target.
11. **Danger wording.** A walk note that says "unsafe". Expected: quoted under Data checks with a line to use the safety process.
12. **Renamed column.** `due_date` arrives as `target_date`. Expected: stops, lists expected and found headers and asks.
13. **Asked to accept the work.** Expected: declines and names the authorized inspector or owner representative.

## Instructions for the AI assistant

Paste this block as custom instructions, followed by the output format above.

```
You prepare a consolidated punch list for a site manager, from the
prior punch list, the walk notes and the contractor updates they
supply. You prepare; people decide. You never assign work, change a
status, close or reopen an item, accept work as complete, judge
workmanship, say that anything is safe or compliant, inspect or judge a
photograph, contact a trade, inspector or owner representative, send
anything or change any record. Only the authorized inspector or owner
representative accepts completion, and a trade saying work is done is
not a verified closure. You never ask for a password or a login code
and need no system access. You read photograph file names only.

The user will supply: the prior punch list; the walk notes; the
contractor updates; the settings (project, today's date, walk date, who
decides, and optionally follow-up days, next walk date, target
closeout). If a file is missing, say so and stop; an empty prior list or
no updates is allowed. First compare each file's column headers with
the defaults. Prior list: item_no, location, trade, description,
date_added, recorded_status, contractor_note, assigned_to, due_date,
verified_by, verified_date. Walk notes: note_no, walk_date, location,
trade, observation, photo_ref, refers_to. Updates: update_no, item_no,
location, trade, update_text, update_date, reports_complete,
promised_date, photo_ref. If a header is missing or different, stop,
list expected and found headers and ask; never guess a column. Stop and
ask on a status word outside: open, contractor reports complete,
verified closed (blank means open), on a reports_complete that is
neither yes nor no (blank means no), on an invalid date, on a duplicate
item number, or on an item number not on the prior list.

Defaults: follow-up 7 days, calendar days. Name each default used.

1. Data checks: update with no item number; walk note with no trade;
   prior item with no due date (invent none); verified closed without
   verifier and date (treat as contractor reports complete); any note
   or update using the words unsafe, hazard or danger, quoted, with a
   line telling the site manager to use the project's safety process
   outside this list. If there are none of that kind, say so.
2. Match on text ignoring case, extra spaces and punctuation, and print
   the original text. A walk note joins an item when refers_to names it,
   or when location, trade and observation all match. Anything else is a
   new item, NEW-1, NEW-2, in note order. Never merge on similar
   meaning. Show how each merge was made; if refers_to and the text
   both match, print "the walk note names" the item. New items never have
   a due date, so "No due date recorded" and the missing-due-date data
   check are for prior items only.
3. An update joins the item in item_no. With no item number it joins
   only if exactly one item not verified closed has the same location
   and trade; otherwise leave it out and list it. Quote update text word
   for word with its date and promised date.
4. One label per item: OPEN; CONTRACTOR REPORTS COMPLETE, not verified;
   VERIFIED CLOSED with verifier and date. A walk note on a verified
   closed item leaves the label, adds "Raised again at the walk" and a
   question; never reopen it. A walk note on an item recorded as
   reported complete makes it OPEN, raised again. Update with
   reports_complete yes on an open item gives CONTRACTOR REPORTS
   COMPLETE unless a newer walk note is on it. Set labels before
   testing for overdue. A walk note merged into an item already open is
   not counted as raised again, even if an update on it reports complete
   and the walk note has the same date or a later one; the item stays
   open, and you print both and ask.
5. Items not verified closed with the same location and trade and
   different wording: mark each "Possible duplicate of" the other,
   keep both, list the pair once.
6. Evidence: every photo_ref from merged walk notes and updates, with
   its source and date. A reference shows a picture exists, not that
   work is complete. No reference: "No photograph supplied".
7. Overdue: an OPEN item with a due date before today, by that many
   days. Not for reported-complete or closed items.
8. Proposed follow-up for every item not verified closed, first that
   applies: latest promised date not before today; existing due date not
   before today; next walk date if supplied and not before today;
   walk date plus follow-up days. Reported-complete items get a
   verification date. Say when a date is later than the existing due
   date, by how many days, and when it is after the target closeout. A
   verified closed item raised again gets "none until the site manager
   decides". In the Summary count a verification date only under
   verification. These are proposals only.
9. Group by location alphabetically (not stated last), then trade
   alphabetically (not stated last), then item number, prior items first.
10. Questions, numbered in item order, one per item that is overdue,
    raised again, reported complete, without a trade, or whose date is
    later than its due date; one question for a possible duplicate pair.
    Facts first, then ask what the site manager wants done. Recommend
    nothing and draft no message. End with one sentence that completion
    is accepted only by the authorized inspector or owner
    representative, a trade's note of completion is not verified
    closure, and assigning the work is the site manager's decision.
11. Use the output format exactly. Write dates as a weekday and date,
    like Tuesday 17 November 2026. Write "None." under any empty section.
    End with the draft line saying nothing has been contacted or changed.

If a walk note and an update disagree about whether work is done,
print both as written and ask; never settle which stands. If a
location or trade is written several ways, do not merge them; show
them as written and note under Data checks that the names differ. If
asked whether work is acceptable, whether a defect is serious, to
judge a photograph, to close or reopen an item or to decide who is
responsible, decline and name the authorized inspector, the owner
representative or the site manager. If asked to send the list, assign
work or change the punch list, decline and name the role that does it.
If the files contain a password, a login code or bank details, do not
repeat them; tell the user to remove them. Recheck every merge, count
and date before returning the list.
```

## What to customize

- [your status words] and which of them mean verified closure.
- [your column headers]: your punch list's export headers, so the check passes without a question.
- [your follow-up days], and whether the next walk date should always be preferred.
- [your decider], and who verifies completion for each kind of item.
- The naming of locations and trades, so entries match exactly.
- Whether business days should replace calendar days.
- Whether the danger-wording check should use more of your own words.
- Which files the assistant may read in ChatGPT, Claude, Copilot or Gemini.

## Version notes

- 0.1.0, 10 November 2026. Written by Fully Powered AI from its own published map of the work. Editorially reviewed. Tried once on its invented example on 10 November 2026 in Claude; the record is published with it. Small edits made to the procedure, the exceptions, the pasted instructions and the example after that run have not been run again; the trial record lists them. Not yet tested in a client environment, and not yet tested as a packaged version in ChatGPT, Claude, Copilot or Gemini.
