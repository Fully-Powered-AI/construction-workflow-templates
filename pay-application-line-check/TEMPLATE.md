# Pay application line check

Workflow template, version 0.1.0.

## Purpose

Compare a progress billing, line by line, with the project's own records before it goes on: the schedule of values, what the last certificate paid, the changes the log shows as approved and the progress evidence supplied with the application. The result is one page of differences, each with its amount, the line it sits on, whether it causes another difference and the role to ask. The assistant compares and lists. It never says which figure is right, certifies a completion percentage, interprets a contract term, restates the amount due or changes a record.

## When to use it and when not to

Use it when a pay application arrives for review and the project has a schedule of values, a change log and a prior certificate to compare it with. It can run again on a corrected application.

Do not use it to prepare an invoice for a client to read (see client billing summary), to review time and expense entries before billing, to approve or reject a change, or to decide whether work is complete. It gives no legal advice and does not read the contract: a question about what a clause means, how retainage works or whether notice is due goes to the people who answer it. It is not for a first application with no schedule of values, or when the documents belong to different projects.

## Roles

- **Runs it:** the project accountant, or the project manager where the project has no accountant.
- **Verifies every figure against the documents:** the project accountant.
- **Maintains the change log and answers questions on changes:** the project manager.
- **Supplies and explains the progress evidence, including the delivery records that support stored materials:** the superintendent or the project engineer.
- **Answers questions on the application's figures:** the contractor's billing contact.
- **Decides payment and whether completion is accepted:** the authorized certifier, as the project's own arrangements name them.

## Inputs

Each input is a spreadsheet export, pasted rows or a clear list, with the headers below. If a header does not match, stop and ask: name the header found and the one expected, and do not guess a column. Amounts are read to the cent. A value that is not a number stops the check on that row; ask.

1. **The pay application.** Fields: Application number, Period to, Original contract sum, Retainage, Total earned less retainage, Less previous certificates for payment, Current payment due. Lines, with the headers `Line`, `Description`, `Scheduled value`, `Previous billed`, `This period`, `Stored materials`, `Total completed and stored`, `Percent complete`, `Balance to finish`, and a `Totals` row. If the lines or the totals row are missing, stop.
2. **The schedule of values,** with `Line`, `Description`, `Scheduled value`. If missing, stop.
3. **The change log,** with `Change`, `Description`, `Amount`, `Status`, `Approval date`, `Line`. A negative amount is a deduction. If missing, say "change log not supplied", skip group C and treat every difference in scheduled values as unexplained.
4. **The prior certificate,** with its number, its total earned less retainage (the cumulative amount certified to date, not that period's payment alone) and the headers `Line`, `Certified to date`. If missing, say "prior certificate not supplied" and skip group B and the previous-certificates check.
5. **The progress evidence,** with `Line`, `Source`, `Date`, `Percent complete`, `Stored materials supported`. One row per line at most; a line with no row has no evidence. If missing, every line is reported as "no evidence supplied".
6. **Settings from the project accountant:**
   - Evidence tolerance in percentage points. Default 0.50.
   - Retainage rate and the amount it applies to. Default: none, so retainage is reported as not checked. If given, the base defaults to total completed and stored.
   - The status words in the change log that count as approved. Default: Approved.

## The procedure

1. **Check the set belongs together.** All documents name the same project. The application number is one more than the prior certificate's. Line numbers are unique within each document. Every application line is in the schedule of values, or is named as the line of a change in the log. A line that is neither is listed in group C as "line not in the schedule of values or the change log" and checked as far as the other inputs allow. If the project, the numbering or a duplicate does not agree, stop and ask.
2. **Arithmetic on the page (group A).** For each line: previous billed + this period + stored materials equals total completed and stored. Percent complete equals total completed and stored over scheduled value, to two decimals. Balance to finish equals scheduled value less total completed and stored. Check percent and balance against the total as shown; if the total is itself wrong, say the other two follow from it and do not list them separately. For the totals row: each column equals the sum of its lines, and previous billed + this period + stored equals total completed and stored.
3. **Previous billing (group B).** Previous billed on each line equals the line's figure on the prior certificate. List each difference with its amount, and say if the previous-billed total differs for the same reason.
4. **Changes (group C).** The expected scheduled value for a line is its schedule-of-values amount plus the amounts of changes against that line whose status is an approved word. Compare the application's scheduled value with it. Then list: an approved change not on the application, a change not approved but included, and a change whose line is not on the application. Compare the scheduled value total with the schedule of values total plus all approved changes, and say which items explain the difference. Report a status as the log states it; never judge whether a change should be approved.
5. **Progress evidence (group D).** For each line, the claim is total completed and stored less stored materials, over scheduled value. Compare it with the evidence percentage. The claim uses the scheduled value as the application shows it, not the schedule of values plus approved changes. List a line when the claim exceeds the evidence by more than the tolerance. Where the claim is below the evidence by more than the tolerance, list that too, as claim below evidence. For each, give the points of difference, the amount the evidence implies (evidence percentage times scheduled value) and the amount in question (claim less that amount). A line billed this period or earlier with no evidence row is listed as "no evidence supplied" with the amount billed to date. Do not say which percentage is correct.
6. **Stored materials (group E).** For each line with stored materials, compare the amount billed with the amount the evidence supports. List a shortfall as unsupported, with the amount. Stored materials on a line with no support at all are unsupported in full. The role to ask is the superintendent, who holds the delivery records.
7. **Retainage and amount due (group F).** If a rate was supplied: retainage equals rate times the base, using the totals as shown. Total earned less retainage equals total completed and stored less retainage. Current payment due equals total earned less retainage less previous certificates for payment. Compare the application's previous certificates for payment with the prior certificate's total earned less retainage (the cumulative amount certified to date). If no rate was supplied, say retainage was not checked and check only the arithmetic from total earned to amount due as stated.
8. **Link causes.** When one difference produces another (a wrong line total produces a wrong column total; a previous-billed error produces a previous-certificates error), number them in order and write "Follows from item N" on the second, or "Follows from items N and M" where several cause it. Count it as a difference, but do not ask a second question about it. A link may rest on a calculation through a supplied setting, such as the retainage rate applied to a previous-billed difference; mark it the same way.
9. **List what agreed.** One short paragraph naming the checks that agreed, and the lines with no difference at all.
10. **Close.** State the amount due as the application states it, say whether the page's own arithmetic agrees, and say the comparison does not restate it. Name anything not checked and why. If a retainage rate was supplied, say it was used as supplied and not checked against the contract. End with the decision line.

## Exceptions and stop conditions

- **A header does not match, a number is not a number, a required input is missing, or the documents name different projects or out-of-sequence applications:** stop and ask. Make no comparison from a guess.
- **Two figures disagree and nothing in the inputs says which is right:** list both with the difference. Do not choose.
- **A change status the log does not state, or a status word not in the approved list:** treat it as not approved and say so in the line.
- **A change amount on the log differs from the amount billed on the application for the same change:** list both amounts in group C.
- **A question about what the contract requires, how retainage or stored materials should be treated, whether a notice is due, whether work is complete or whether to pay or withhold:** decline, and name the role who answers it.
- **Asked to certify a percentage, restate the amount due, fill a missing figure, correct the application, approve a change, post an entry or send the page to the contractor:** decline. The project accountant decides what is taken further and sends it.
- **A password or login code appears in what was supplied:** do not use it, tell the person to remove it, and never ask for one.
- **Nothing differs:** print "No differences found" in every group, with the list of checks that agreed. Do not invent a finding.

## Output format

```
PAY APPLICATION LINE CHECK: [project], application [n], period to [date]

Prepared for: [project accountant or manager]. Basis: application [n] dated [date]; schedule of values ([version or date]); change log as of [date]; prior certificate [n] dated [date]; progress evidence from [sources and dates].
Settings used: evidence tolerance [x] points; retainage [rate and base, or "rate not supplied"]; approved status word: [words].

Totals: [n] lines checked. [n] differences: [n] on lines [list] (a difference that sits on one line of the application), [n] on page figures (the totals row, the scheduled value total and the application's own fields such as previous certificates). Lines with no difference: [list, or "none"].

Checks that agree: [short paragraph naming each check that agreed].

A. Arithmetic on the page
[n]. [Line or total, the figure]: shown [x]; the parts give [y]; difference [z]. [Follows from item N (or items N and M), if so.] Ask: [role].
(If none: "None found.")

B. Previous billing against the prior certificate
[n]. Line [nn], previous billed: application [x]; prior certificate [y]; difference [z]. Ask: [role].
(If none: "None found." If no certificate: "Prior certificate not supplied.")

C. Changes against the schedule of values
[n]. [Change or line]: [status], [amount], [what the application shows against what the log and schedule give]. Ask: [role].
(If none: "None found." If no log: "Change log not supplied.")

D. Progress evidence
[n]. Line [nn]: claimed [x]% ([amount] over [scheduled value]); evidence [y]% ([source], [date]); [z] points [above or below]. Evidence implies [amount]; claimed [amount]; amount in question [amount]. Ask: [role].
[n]. Line [nn]: no evidence supplied. Billed to date [amount]. Ask: [role].
(If none: "None found.")

E. Stored materials
[n]. Line [nn]: billed [x]; supported [y] ([source], [date]); unsupported [z]. Ask: superintendent.
(If none: "None found." If none billed: "No stored materials billed.")

F. Retainage and amount due
[n]. [Figure]: application [x]; [expected y, or prior certificate y]; difference [z]. [Follows from item N (or items N and M), if so.] Ask: [role].
(If none: "None found." If no rate: "Retainage not checked: no rate supplied.")

Amount due as stated: [amount]. The page's own arithmetic from retainage to amount due [agrees / does not agree: see item N]. This comparison does not restate it.

Not checked: [each thing and why, including a supplied retainage rate (used as supplied, not checked against the contract), or "Nothing left unchecked."]

The project accountant verifies each figure against the documents. [Certifier role] decides payment and completion. This comparison certifies no completion percentage, interprets no contract term and changes no record.
```

## Reviewer checklist

1. Every figure on the page traces to a supplied document, and the project accountant has checked the listed amounts against those documents. (Project accountant)
2. Each arithmetic difference is recomputed by hand and agrees. (Project accountant)
3. Changes are reported with the status the log states, and none is judged. (Project manager)
4. Each evidence difference names its source and date, and the amount in question is the claim less the implied amount. (Superintendent)
5. A difference that follows from another is marked as such and counted once as a cause. (Project accountant)
6. Nothing says which of two figures is correct, restates the amount due or recommends paying, withholding or approving. (Project accountant)
7. Every group is present, and an empty group says so. (Project accountant)
8. The decision line names the role that decides. (Project accountant)

## Acceptance tests

Proposed tests. None has been run.

1. **Clean application.** Every line adds, matches the certificate and the schedule, and the evidence agrees. Expected: "No differences found" in each group, with the list of checks that agreed.
2. **Line does not add.** Previous 27,000, this period 18,000, stored 0, total shown 46,000. Expected: a group A item with a 1,000 difference, and the percent and balance noted as following from the shown total.
3. **Previous billing differs.** Application 8,000, certificate 6,000. Expected: a 2,000 difference in group B, and the previous-certificates difference marked as following from it.
4. **Approved change missing.** An Approved change of 6,000 on a line whose scheduled value was not raised. Expected: a group C item showing the expected scheduled value.
5. **Pending change billed.** A change with status Pending included in a scheduled value. Expected: listed in group C, status reported as stated, no judgement on whether it should be approved.
6. **Evidence below claim.** Claim 51.11%, evidence 40.00%, scheduled value 90,000. Expected: 11.11 points, implied amount 36,000, amount in question 10,000; no statement of which is right.
7. **No evidence for a line.** Expected: "no evidence supplied" with the amount billed to date.
8. **Stored materials short.** 12,000 billed, 9,500 supported. Expected: 2,500 unsupported.
9. **Header mismatch.** The change log has "Value" in place of "Amount". Expected: stop, name both headers, ask; no comparison.
10. **No retainage rate.** Expected: "Retainage not checked: no rate supplied", with the amount-due arithmetic still checked.
11. **Asked to certify or restate.** "Is 92% complete right, and what should we pay?" Expected: declines, lists the difference with its figures, names the certifier.

## Instructions for the AI assistant

Paste this block as custom instructions, followed by the output format above.

```
You compare one construction pay application with the project's own
records, line by line, and list the differences. You never certify a
completion percentage, say which of two figures is right, restate the
amount due, interpret a contract term, approve a change, correct the
application, post an entry or send anything. A person approves anything
that is sent, posted, paid or changed in a record. Never ask for a
password or a login code.

The user will supply: the pay application (fields, lines with headers
Line, Description, Scheduled value, Previous billed, This period,
Stored materials, Total completed and stored, Percent complete, Balance
to finish, and a Totals row); the schedule of values (Line, Description,
Scheduled value); the change log (Change, Description, Amount, Status,
Approval date, Line); the prior certificate (number, total earned less retainage to date,
Line, Certified to date); the progress evidence (Line, Source, Date, Percent
complete, Stored materials supported); and settings (evidence tolerance,
default 0.50 points; retainage rate and base; approved status words,
default Approved). If a password or login code appears in what was
supplied, do not use it and tell the person to remove it. If a header does not match, a number is not a
number, the application or schedule of values is missing, or the
documents name different projects, or the application number is not one
more than the prior certificate's, stop and ask. Do not guess a column. If the change log is not supplied, say so,
skip the changes check and treat scheduled value differences as
unexplained. If the prior certificate is not supplied, say so and skip the
previous billing check and the previous-certificates comparison. If the
progress evidence is not supplied, report every line as "no evidence
supplied". A line that is in neither the schedule of values nor the change
log goes in the changes group as "line not in the schedule of values or the
change log", checked as far as the other inputs allow.

1. Arithmetic: per line, previous + this period + stored = total; percent
   = total / scheduled value; balance = scheduled value - total. Check
   percent and balance against the total as shown. Totals row: each column
   equals the sum of its lines, and its parts add to its total.
2. Previous billing: each line against the prior certificate.
3. Changes: expected scheduled value = schedule of values + changes with
   an approved status on that line. List approved changes missing,
   unapproved changes included, and the scheduled value total difference.
   Report status as stated; never judge it. A status the log does not
   state, or a word not in the approved list, counts as not approved; say
   so on the line.
4. Evidence: claim = (total - stored) / scheduled value, using the
   scheduled value as the application shows it. List differences
   beyond the tolerance, either direction, with points, the implied amount
   (evidence % x scheduled value) and the amount in question. List lines
   with no evidence, with the amount billed to date.
5. Stored materials: billed against supported; list the unsupported amount.
   Stored materials on a line with no support row are unsupported in full.
   Ask the superintendent.
6. Retainage and amount due: with a rate, retainage = rate x base; total
   earned less retainage; amount due = that less previous certificates;
   compare previous certificates with the prior certificate's total earned
   less retainage (cumulative, not that period's payment).
   Without a rate, say retainage was not checked.
7. Mark a difference that follows from an earlier one "Follows from item
   N" (or "items N and M"); the link may rest on a calculation through a
   supplied setting, such as the retainage rate. Number all items in one sequence across
   groups A to F. Count each difference once, as on a line or on a page
   figure (the totals row, the scheduled value total, previous
   certificates and the application's own fields).
8. Use the output format exactly, with "Checks that agree" after the
   totals line and before group A. Print "None found." in an empty group.
   State the amount due as the application states it and say the
   comparison does not restate it. Under "Not checked", say that a
   supplied retainage rate was used as supplied and not checked against
   the contract, and name anything else not checked and why. End with the
   decision line naming the certifier role.

When two figures disagree and nothing says which is right, list both.
Questions about what the contract requires, whether to pay or withhold,
or whether work is complete: decline and name who answers.
```

## What to customize

- The column headers, if your forms use different ones, mapped once in a line at the top of the instructions.
- The evidence tolerance, the retainage rate and the amount it applies to, and the status words your change log uses for approved.
- Who is asked about each kind of difference, and the name of the certifier role.
- Whether groups C and E are kept, for projects with no change log or no stored materials.
- Which exports the assistant may read in ChatGPT, Claude, Copilot or Gemini.

## Version notes

- 0.1.0, 10 November 2026. Written by Fully Powered AI from its own map of the work. Tried once on its invented example in Claude on 10 November 2026; the record is published with it (`public/trial.md`). Changed after an independent review the same day and not run again; the record lists where its output differs from the template as it now stands. Not yet tested in a client environment.
