# Submittal register review

Workflow template, version 0.1.0.

## Purpose

Prepare one dated register of the submittals a project requires: for each, the latest package received, the review status exactly as the log records it, the documents still missing, whether it has been routed, and, against the date its order must be placed, whether there is time left for review. The register also lists the long-lead items not yet accepted and puts numbered questions to the project engineer. The assistant prepares; it never routes a package, records or changes a status, accepts or rejects anything, reviews technical content, certifies compliance with the specifications, contacts a trade or reviewer, or releases an order. The project engineer verifies routing and the authorized design reviewer accepts or rejects each submittal.

## When to use it and when not to

Use it when a submittal arrives, before the weekly procurement or coordination meeting, and when a material release is coming up. Run it again after the log changes.

Do not use it:

- to judge whether a product meets the specifications. That is the design reviewer's decision, and the assistant reads no technical content;
- to treat a submitted package as an approved material. A package that has been received is not an accepted one;
- to track supplier delivery dates once an order is placed. That is a separate comparison, supplier delivery date check;
- to review a supplier's renewal or contract terms. That is vendor renewal review;
- to decide a substitution. A substitution request stays open until the design reviewer records a decision.

## Roles

- **Runs it:** the project engineer, or the project coordinator working for them.
- **Verifies routing and settles every question:** the project engineer, or [your decider].
- **Accepts or rejects each submittal:** the authorized design reviewer, as the contract names them. Always a person.
- **Prepares and sends packages:** the trade named on the required list.
- **Releases orders:** purchasing, or the project manager. Always a person.
- **Updates the log and the schedule:** the people the project names, after any decision.

## Inputs

The assistant works only from the files and notes the person supplies. It needs no connection to the project management system and never asks for a password or a login code.

1. **The required submittals.** One row per submittal the specifications call for. Default column headers: `submittal_no`, `spec_section`, `description`, `trade`, `required_documents`. `required_documents` is a list separated by semicolons, for example `product data; shop drawings; samples`. If missing, stop.
2. **The submittal log.** One row per package received, one row for each revision. Default column headers: `submittal_no`, `revision`, `received_date`, `documents_received`, `routed_to`, `routed_date`, `recorded_status`, `status_date`, `reviewer_comment`, `substitution`. `revision` is a whole number, 0 for the first package. `documents_received` is a semicolon list written with the same names as the required list. `recorded_status` is exactly one of `received`, `with reviewer`, `approved`, `approved as noted`, `revise and resubmit` or `rejected` ([your status words]), or blank. `substitution` is `yes` or `no`; blank is read as `no`. A submittal with no row has not been received. An empty log is allowed.
3. **The procurement dates.** One row per submittal. Default column headers: `submittal_no`, `order_by_date`, `lead_time_days`. `order_by_date` is the last date the order can be placed and still meet the schedule, supplied by purchasing. A blank date or lead time is read as not supplied.
4. **The settings,** typed: the project, today's date and who decides. Also the review period in days (default 14, [your review days]), the extra days a resubmission or a missing document adds (default 7, [your resubmission days]) and the lead time at or above which an item is long-lead (default 56 days, [your long-lead threshold]). Days are counted as calendar days. Each default used is named after "Defaults used" on the Settings line.

**Column check.** Before any other work, compare each file's headers with the defaults, or with the project's own headers if [your column headers] are set. If a header is missing or named differently, stop. List the headers expected and the headers found, ask which column is which, and prepare nothing else. Never guess a column.

## The procedure

1. **Check the inputs.** Run the column check. Confirm today's date. A status that is not one of the allowed words, a date that is not a real date, two required rows with the same number, or two log rows with the same number and revision: stop and ask.
2. **Check the data.** List under Data checks, and leave out of the register: a log row or procurement row whose number is not on the required list. Also list, but keep: a submittal with no procurement row (order date and lead time not supplied; no risk is calculated for it); a document received that is not on the required list for it; a `with reviewer` row with no `routed_date`; and an accepted package with a missing document.
3. **Take the latest package.** For each required submittal, use the log row with the highest revision. Earlier revisions are listed only as "Earlier revisions: revision [n] [status], recorded [date]". A submittal with no row is NOT RECEIVED.
4. **Set the status label.** Exactly one, from the latest package: ACCEPTED (`approved`, `approved as noted`), RETURNED (`revise and resubmit`, `rejected`), WITH REVIEWER (`with reviewer`), RECEIVED (`received`), NO STATUS RECORDED (blank), or NOT RECEIVED. Print the recorded words beside ACCEPTED and RETURNED. Print a reviewer comment word for word in quotation marks; never summarise it or read it as an acceptance. A status is only what the log records.
5. **Check the documents.** Compare `documents_received` with `required_documents` item by item, ignoring case and spaces. A required item not received is missing. For NOT RECEIVED, every required item is missing. Print "Documents complete" or "Documents missing [n] of [total]".
6. **Check the routing.** List under Routing to verify, in submittal-number order, every latest package that is: (a) RECEIVED or NO STATUS RECORDED with no `routed_to`, with the days since `received_date`; (b) WITH REVIEWER for more days than the review period, counting from `routed_date`, with the days and how far over; (c) RETURNED with no newer revision, with the days since `status_date`, noting that the log does not show whether the return reached the trade. A package WITH REVIEWER inside the period is shown on its register line with its days and is not listed.
7. **Work out the time left,** for every submittal that is not ACCEPTED and has both dates. Days away = `order_by_date` − today. Days needed = the review period, plus the resubmission days when the package is NOT RECEIVED, RETURNED or has a missing document. The review period is counted in full, even for a package already with the reviewer and part-way through it; it is a conservative allowance, not a forecast. Spare days = days away − days needed. If spare days are below zero the submittal is AT RISK, short by that many days. If `order_by_date` is before today, write PAST ORDER DATE and the days past, and treat it as AT RISK. Print days away, days needed and the result on the register line. Never state or imply when a reviewer will finish.
8. **Mark the long-lead items.** A submittal with `lead_time_days` at or above the threshold is long-lead. List those not ACCEPTED under Long-lead items not yet accepted, AT RISK first, then by order date. An accepted long-lead item is not listed.
9. **List what is at risk,** under At risk before the order date, with the largest shortfall first, then by order date. Each line gives the submittal, the days short and the order date.
10. **List missing documents** under Missing documents, in submittal-number order, naming each missing item.
11. **Note substitutions.** A latest package with `substitution` of `yes` that is not ACCEPTED is marked "Substitution requested" on its register line and counted in the summary. It is never treated as a decided substitution.
12. **Write the questions,** numbered, in submittal-number order, one for each submittal that is AT RISK, appears under Routing to verify, has a missing document or is NOT RECEIVED. A submittal with several reasons shares one question. Each states the facts first (status, days, documents, the order date and the time left) and then asks what the project engineer wants done about the matter it names (routing, a missing document, the time left, a resubmission). A question names no action, recommends nothing and offers no wording for a message. Close the questions with one sentence saying that acceptance rests with the authorized design reviewer, that nothing here accepts a material, and that releasing an order is purchasing's decision.
13. **Return the register** to the person who ran it, for [your decider]. A person contacts the trades and the reviewers, and a person updates the log.

## Exceptions and stop conditions

- **A column header is missing or named differently:** stop; list expected and found headers; ask.
- **A status word that is not allowed, an invalid date, a duplicate number, or a duplicate number and revision:** stop and ask.
- **A package is logged as received with no documents listed:** treat every required item as missing and note it under Data checks.
- **A reviewer comment that reads like an acceptance but a status that is not accepting, or the reverse:** print both as recorded and ask; never settle which stands.
- **A date that cannot be read, such as "next week":** treat it as not supplied and show the words.
- **Asked to say whether a product complies, to review a drawing or datasheet, to predict how long a reviewer will take, or to mark a package accepted:** decline and name the authorized design reviewer or the project engineer.
- **Asked to send the register to a trade, release an order or change the log:** decline and name the role that does it.
- **The files contain a password, a login code or bank details:** do not repeat them; tell the person to remove them from the source.

## Output format

```
SUBMITTAL REGISTER REVIEW: [project], [weekday date]

For: [decider role]. Prepared [weekday date] from: required submittals ([n] rows), submittal log ([n] rows), procurement dates ([n] rows), settings.
Column check: [all headers matched].
Settings: review period [n] days, resubmission [n] days, long-lead threshold [n] days, counted in calendar days. Defaults used: [list / none].
Summary: [n] required submittals. Accepted [n] (approved [n], approved as noted [n]). With reviewer [n]. Received, not with reviewer [n]. Returned [n]. Not received [n]. Submittals with missing documents: [n] (received [n], not received [n]). Routing to verify: [n]. Long-lead not yet accepted: [n], of which [n] at risk. At risk before the order date: [n]; past the order date: [n]. Substitutions requested and not accepted: [n].

Data checks
- [Each check, with what was done / None.]

Register
- [Number] [spec section] [description], [trade]. [Revision [n] received [weekday date] / NOT RECEIVED]. [STATUS LABEL][: recorded words, recorded [weekday date]] [since [routed_date as weekday date] ([reviewer]), [n] days]. [Documents complete / Documents missing [n] of [total]]. [Substitution requested.] [Earlier revisions: revision [n] [status], recorded [weekday date].] [Reviewer comment: "[words]".] [Long-lead, [n] days.] [Order by [weekday date], [n] days away; review [and resubmission] need[s] [n] days; [n] spare days / AT RISK, short [n] days / PAST ORDER DATE by [n] days / order date not supplied.]

Missing documents
- [Number] ([trade]): [items]. [Nothing received.]

Routing to verify
- [Number]: [reason, with days].

Long-lead items not yet accepted: [n]
- [Number] [description]: [AT RISK, short [n] days / [n] spare days] (order by [weekday date]). [Status and one fact.]

At risk before the order date: [n]
- [Number] [description]: short [n] days; order by [weekday date].

Questions for the [decider role]
1. [Number] [description] ([trade]). [Facts.] [Question.]
[Closing sentence on acceptance and orders.]

Draft for the [decider role]'s decisions. No trade, reviewer or supplier has been contacted, and no log, status or order has been changed.
```

Write [weekday date] like Monday 16 November 2026. Everything the instructions require has a place above. Print the Long-lead slot only on a submittal that is not ACCEPTED; an accepted long-lead item carries no Long-lead slot. Where a section has nothing in it, print "None." under its heading.

## Reviewer checklist

1. Every required submittal appears once, in number order, with the status words exactly as the log records them. (Project engineer)
2. The latest package is the highest revision, and earlier revisions are only noted. (Project coordinator)
3. Missing documents match the required list item by item. (Project engineer)
4. Days away, days needed, spare days and days short match a calendar. (Project engineer)
5. Every package that is not routed, overdue with a reviewer, or returned without a resubmission is under Routing to verify. (Project engineer)
6. The long-lead and at-risk lists are complete, sorted as stated, and the counts in the summary agree with them. (Purchasing)
7. No comment, status or substitution has been read as an acceptance, and no technical judgment appears. (Project engineer)
8. Nothing has been sent, accepted, ordered or changed. (Project engineer)

## Acceptance tests

Proposed tests. None has been run.

1. **Ordinary week.** Every submittal received, complete and accepted, with order dates well ahead. Expected: all lines ACCEPTED, every list prints "None.", no questions.
2. **Missing document.** A package lists two of three required items. Expected: "Documents missing 1 of 3", the item named under Missing documents, a question.
3. **Never received.** A required submittal with no log row. Expected: NOT RECEIVED, every item missing, time left calculated with the resubmission days.
4. **Never routed.** A package received with no reviewer. Expected: listed under Routing to verify with the days since receipt.
5. **Late with the reviewer.** A package with a reviewer for longer than the review period. Expected: listed with days and days over; no prediction of when the reviewer will finish.
6. **Spare days exactly zero.** Days away equal days needed. Expected: "0 spare days", not at risk.
7. **Past the order date.** An order date before today and no acceptance. Expected: PAST ORDER DATE with the days, and AT RISK.
8. **Accepted long-lead item.** Expected: not listed under long-lead items.
9. **Approved-looking comment.** A reviewer comment says "looks fine" while the status is `with reviewer`. Expected: both printed as recorded, no acceptance inferred, a question.
10. **Substitution requested.** Expected: marked on the register line, counted, never treated as decided.
11. **Renamed column.** `order_by_date` arrives as `buy_date`. Expected: stops, lists expected and found headers and asks.
12. **Asked whether a product meets the specification.** Expected: declines and names the authorized design reviewer.

## Instructions for the AI assistant

Paste this block as custom instructions, followed by the output format above.

```
You prepare a submittal register review for a project engineer, from the
required submittals, the submittal log and the procurement dates they
supply. You prepare; people decide. You never route a package, record or
change a status, accept or reject a submittal, review technical content,
certify that anything complies with the specifications, contact a trade,
reviewer or supplier, release an order, send anything or change any
record. Only the authorized design reviewer accepts or rejects a
submittal, and a package received is not an accepted material.
You never ask for a password or a login code and need no system access.

The user will supply: the required submittals; the submittal log; the
procurement dates; the settings (project, today's date, who decides,
and optionally the review period, resubmission days and long-lead
threshold). If a file is missing, say so and stop. First compare each
file's column headers with the defaults:
required: submittal_no, spec_section, description, trade,
required_documents. Log: submittal_no, revision, received_date,
documents_received, routed_to, routed_date, recorded_status,
status_date, reviewer_comment, substitution. Procurement: submittal_no,
order_by_date, lead_time_days. If a header is missing or different, stop,
list expected and found headers and ask; never guess a column. Stop and
ask on a status word outside: received, with reviewer, approved,
approved as noted, revise and resubmit, rejected (blank allowed), on a
date that is not a real date, or on a duplicate submittal or revision.
A date that cannot be read at all, such as "next week", is not an error:
treat it as not supplied and show the words.

Defaults: review period 14 days, resubmission 7 days, long-lead 56 days,
calendar days. Name each default used.

1. Data checks: leave out log or procurement rows whose number is not on
   the required list. Keep but list: no procurement row (no risk
   calculated), a document not on the required list, a with-reviewer row
   with no routed_date, an accepted package with a missing document. A
   package logged as received with no documents listed: treat every
   required item as missing and note it here.
2. For each required submittal take the highest revision. Earlier
   revisions are noted only. No row means NOT RECEIVED.
3. Label: ACCEPTED (approved, approved as noted), RETURNED (revise and
   resubmit, rejected), WITH REVIEWER, RECEIVED, NO STATUS RECORDED
   (blank), NOT RECEIVED. Print reviewer comments word for word and
   never read them as acceptance. If a comment reads like an acceptance
   but the status does not accept, or the reverse, print both as recorded
   and ask a question; never settle which stands.
4. Documents: compare received with required item by item, ignoring case
   and spaces. NOT RECEIVED means every item is missing.
5. Routing to verify, in number order: RECEIVED or NO STATUS RECORDED
   with no routed_to (days since received); WITH REVIEWER longer than
   the review period (days, days over); RETURNED with no newer revision
   (days since status_date; the log does not show whether it reached the
   trade).
6. Time left, for every submittal not ACCEPTED with both dates: days
   away = order_by_date - today. Days needed = review period, plus the
   resubmission days if NOT RECEIVED, RETURNED or a document is missing;
   count the review period in full even if part of it has passed.
   Spare = away - needed. Below zero is AT RISK, short by that many days.
   An order date before today is PAST ORDER DATE and AT RISK. Never
   predict when a reviewer will finish.
7. Long-lead: lead_time_days at or above the threshold. List those not
   accepted, AT RISK first then by order date. List AT RISK items with
   the largest shortfall first, then by order date. Missing documents in
   number order, naming each item. Print the Long-lead tag on the
   register line only for a submittal not ACCEPTED.
8. A latest package with substitution yes that is not ACCEPTED is marked
   "Substitution requested", counted, and never treated as decided.
9. Questions, numbered in number order, one per submittal that is AT
   RISK, under Routing to verify, missing a document or NOT RECEIVED.
   Facts first, then ask what the project engineer wants done about the
   matter named (routing, a missing document, the time left, a
   resubmission), naming no action. Recommend nothing and draft no
   message. End with one sentence that acceptance rests with the
   authorized design reviewer, nothing here accepts a material, and
   releasing an order is purchasing's decision.
10. Use the output format exactly. Write dates as a weekday and date,
    like Monday 16 November 2026. Write "None." under any empty section.
    End with the draft line saying nothing has been contacted or changed.

If asked whether a product complies, to review a drawing or data sheet,
to predict a reviewer's timing or to mark a package accepted, decline and
name the authorized design reviewer or the project engineer. If asked to
send the register, release an order or change the log, decline and name
the role that does it. If the files contain a password, a login code or
bank details, do not repeat them; tell the user to remove them. Recheck
every date and every count of days before returning the register.
```

## What to customize

- [your status words] and which of them count as accepted.
- [your column headers]: your log's export headers, so the check passes without a question.
- [your review days], [your resubmission days] and [your long-lead threshold].
- [your decider], and who verifies routing.
- How late a package may sit with a reviewer before it is listed, if different from the review period.
- Whether days needed for a package already with the reviewer should count only the days left in the review period. As written it counts the full period, which overstates the need for a package well into its review (S-04 in the example is 20 days in and still counted as needing 14).
- Whether business days should replace calendar days.
- The document names, so the required list and the log match exactly.
- Which files the assistant may read in ChatGPT, Claude, Copilot or Gemini.

## Version notes

- 0.1.0, 10 November 2026. Written by Fully Powered AI from its own published map of the work. Editorially reviewed. Tried once on its invented example in Claude on 10 November 2026; the record is published with it. The example's own output was visible during that run, so it was not a blind run. Small edits made after the recorded run have not been run again: the year added to every date in the example, the extra words and the extra Data checks clause removed from the example, the question wording and the example's questions, the full-period rule for days needed stated, the rule on the Long-lead slot, and the typo "Every thing" corrected. Also not run again: the pasted instructions now say to ask when a reviewer comment and a status disagree, to treat a package logged as received with no documents as missing every item, to treat an unreadable date as not supplied, and to name a resubmission among the matters a question may ask about, and the register line's days now say they count from the routing date. Not yet tested in a client environment, and not yet tested as a packaged version in ChatGPT, Claude, Copilot or Gemini.
