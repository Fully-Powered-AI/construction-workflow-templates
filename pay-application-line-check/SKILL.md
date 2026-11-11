---
name: "pay-application-line-check"
description: "Compare a progress billing, line by line, with the project's own records before it goes on: the schedule of values, what the last certificate paid, the changes the log shows as approved and the progress evidence supplied with the application. The result is one page of differences, each with its amount, the line it sits on, whether it causes another difference and the role to ask. The assistant compares and lists. It never says which figure is right, certifies a completion percentage, interprets a contract term, restates the amount due or changes a record."
license: "MIT"
metadata:
  version: "0.1.0"
  publisher: "Fully Powered AI"
  capability: "Pay application line check"
---

# Pay application line check

This is the technical file for a Fully Powered capability template. It carries the instructions an AI product follows. The complete template, with roles, inputs, exceptions, the reviewer checklist, acceptance tests and what to customize, is in [TEMPLATE.md](TEMPLATE.md). A worked example with invented data is in [EXAMPLE.md](EXAMPLE.md).

## Instructions

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

## Before relying on it

Decide every item under "What to customize" in TEMPLATE.md and set the limits the instructions in this file leave open, written in square brackets such as [N], to your own. Then run the acceptance tests in TEMPLATE.md on past work. A person starts this work, supplies the inputs and decides what happens with the result.
