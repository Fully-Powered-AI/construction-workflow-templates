# Lender draw package index

Capability template, version 0.1.0.

## Purpose

Assemble the index of one monthly draw package in the order of the lender's own checklist: for every required document, whether it was listed as supplied, and for every invoice in the draw, whether the accounting ledger agrees. The result is one page. Missing attachments are numbered gaps with the role to ask, and invoice-to-ledger differences are numbered with their amounts and reconciled by budget line. The assistant lists and compares. It never reads an attachment for its content, says whether a waiver, title record or any other document is adequate, states lien status, certifies anything to the lender, decides what the lender will fund, submits the package or changes a record.

## When to use it and when not to

Use it when the monthly draw-preparation date arrives, the period's costs are posted and the attachments have been gathered into a list. It can run again as gaps are closed, so that the finance lead sees what is still open.

Do not use it to check a contractor's progress billing against the schedule of values (see pay application line check), to forecast cash (see thirteen-week cash flow forecast), or to review or write a lien waiver, a title document, a loan agreement or any other legal document. It gives no legal advice: a question about what a document means or whether it is sufficient goes to the people who answer it. It is not for a package whose checklist, draw schedule or ledger export belong to a different project or period.

## Roles

- **Runs it:** the project accountant, or a finance coordinator.
- **Gathers the attachments and answers the questions on missing ones:** the roles named in the Ask column of the checklist.
- **Answers questions on ledger differences:** the role named in the settings, by default the project accountant.
- **Reviews the index, approves submission and sends the package:** the project finance lead.
- **Decides funding:** the lender's reviewers.
- **Reviews legal documents:** counsel or the people the company uses for that work.

## Inputs

Each input is a spreadsheet export, pasted rows or a clear list, with the headers below. If a header does not match, stop and ask: name the header found and the one expected, and do not guess a column. Amounts are read to the cent. A value that is not a number stops the check on that row; ask.

1. **The lender's checklist,** in the lender's order, with `Item`, `Section`, `Document required`, `Scope`, `Required`, `Ask`. Scope is one of Invoice (one document for each invoice in the draw), Payee (one for each payee in the draw) or Draw (one for the whole draw). Required is Yes or No. If Ask is blank, ask the project finance lead. If the checklist is missing, stop.
2. **The draw schedule,** one row for each invoice in the draw, with `Invoice`, `Payee`, `Budget line`, `Amount`. If it is missing, stop.
3. **The accounting export,** with `Invoice`, `Payee`, `Posting date`, `Amount`, `Budget line`, `Status`. If it is missing, stop.
4. **The attachments listed,** one row for each file, with `Item`, `Payee`, `Invoice`, `File name`, `Document date`. Item is the checklist item it serves; Payee and Invoice are blank where the item's scope is Draw. A row with a blank file name does not count as supplied. If the list is missing, stop.
5. **Settings from the project finance lead:**
   - The project, the draw number, and the period start and end. If any is missing, ask.
   - The lender's name and the version or date of its checklist. If either is missing, ask.
   - The date each export was taken: the accounting export "as of" date and the attachment list "as of" date. If either is missing, ask.
   - The total entered on the lender's form. If not given, print "Form total not supplied." in group D and make no comparison.
   - The ledger statuses that count as posted. Default: Posted.
   - The role asked about ledger differences. Default: project accountant.

## The procedure

1. **Check the set belongs together.** The four tables carry no project or period column, so the settings govern: the project, draw number and period come from the settings. Where an input states its own project or period (a file title, a heading or a note), it must agree with the settings. Invoice numbers in the draw schedule are unique for each payee. Every attachment row names an item on the checklist, or is kept for the line "listed but not on the checklist". If a stated project or period does not agree with the settings, or a duplicate is found, stop and ask.
2. **Match invoices.** An invoice matches when its invoice number and payee are the same in both lists, ignoring capitals and spaces at the ends. A number found under a different payee does not match; report it as found under that payee in step 5; that ledger row is reported once, there, and is not listed again in step 6. If the ledger has two rows for one invoice and payee, list both and compare their sum.
3. **Build the index in the lender's order.** For each checklist item, in the order given:
   - Scope Draw: complete if at least one attachment row with that item has a file name and a document date; otherwise missing.
   - Scope Invoice: one attachment row with that item and invoice number is needed for each invoice in the draw schedule. State how many of the invoices have one.
   - Scope Payee: one attachment row with that item and payee is needed for each distinct payee in the draw schedule. State how many of the payees have one.
   - A row with a blank file name does not count as supplied. A row for an item that is not on the checklist counts toward no item; it goes under "Listed but not on the checklist".
   - Status words: Complete, "Incomplete, n of m invoices listed" (or "payees listed"), Missing, or for an item that is not required, Not supplied or Supplied. A Draw item with a file name but no document date is "Missing, listed without a document date: [file name]" and is a gap in step 4. Name the file and date for a Draw item. Never read the file or describe its content.
4. **List the missing attachments.** Each gap in a required item is a numbered line, M1 onward, in checklist order: the item, the document required, the payee or invoice or "the draw", and the role in the Ask column. A missing optional item is not a gap; it appears only in the index.
5. **Compare the draw schedule with the ledger.** For each draw invoice in schedule order, report in one numbered line, D1 onward, anything that differs: not found in the ledger, found under another payee, the amount (state both amounts and the difference), the budget line (state both), or a status that is not one of the posted statuses. Report an invoice that agrees on all of these only in "Checks that agree".
6. **List ledger entries not in the draw.** Each ledger row with a posting date inside the period whose invoice number and payee are not in the draw schedule, other than a row already reported in step 5 as found under another payee, is a numbered line in the same sequence, with its posting date, amount and budget line. Rows outside the period are ignored.
7. **Reconcile by budget line.** For each budget line in either list: the draw schedule's total for the line, the ledger's total for the draw's invoices that were found, placed on the ledger's own budget line, and the difference, draw minus ledger. Name the D numbers that explain the difference. Then the two grand totals and their difference, split into the amounts not found and the amount differences. An invoice found in the ledger with a status that is not posted stays in the ledger totals, because it was found; its status is reported in step 5 only. An invoice found only under another payee does not match, so it counts as not found in the split, and its ledger amount is not in the ledger total. Ledger entries not in the draw (step 6) are left out of the budget-line reconciliation and of both totals.
8. **Compare the draw total with the lender's form.** Sum the draw schedule, compare it with the total entered on the lender's form, and state the difference and which is higher. Give no reason for it. If the form total was not supplied, print "Form total not supplied."
9. **Count and close.** Fill the totals line from the groups; the differences count is every D line, including ledger entries not in the draw. "Checks that agree" names each check that agreed (the set belongs together; the invoices that agree with the ledger in every respect; the Draw items with a file name and a date). "Not checked" always names the contents of every attachment and lien status and title, and then anything else a reader might assume was checked, with the reason. End with the decision line.

## Exceptions and stop conditions

- **A header does not match, a number is not a number, a required input is missing, or an input states a project or period that differs from the settings:** stop and ask. Make no comparison from a guess.
- **The same invoice number appears twice for one payee in the draw schedule:** stop on that invoice and ask the project accountant. Do not choose one.
- **An attachment row serves an item that is not on the checklist:** do not count it toward any item; list it under "Listed but not on the checklist".
- **A payee is named slightly differently in two lists:** report the invoice as found under another payee, with both spellings. Do not decide that they are the same.
- **Asked to read a waiver, a title record or an insurance certificate, say whether it is adequate or whether liens are cleared, or say whether the lender will fund:** decline, and name the role that answers.
- **Asked to submit the package, post or correct a ledger entry, edit the draw schedule to make it agree, or fill a missing document:** decline. The project finance lead decides what is taken further and sends it.
- **A password or login code appears in what was supplied:** do not use it, tell the person to remove it, and never ask for one.
- **Nothing is missing and nothing differs:** print "None found." in groups B and C, with the list of checks that agreed. Do not invent a finding.

## Output format

```
LENDER DRAW PACKAGE INDEX: [project], draw [n], period [start] to [end]

Prepared for: [project finance lead]. Basis: [lender] checklist [version or date]; draw schedule of [n] invoices; accounting export as of [date]; attachments listed as of [date]. (Lender, checklist version or date, and both "as of" dates come from the settings.)
Settings used: statuses counted as posted: [words]; draw amount on the lender's form: [amount, or "not supplied"]; role asked about ledger differences: [role].

Totals: [n] required items: [n] complete, [n] incomplete, [n] missing. [n] optional items: [n] supplied. [n] missing attachments. [n] differences between the draw and the ledger, counting ledger entries not in the draw.

Checks that agree: [short paragraph naming each check that agreed, and the invoices that agree with the ledger in every respect].

A. Index in the lender's order
[Item]. [Section]: [document required] ([each invoice / each payee / the draw])[, optional, for an item that is not required]. [Status: Complete; "Incomplete, [n] of [m] invoices listed" or "payees listed"; Missing; "Missing, listed without a document date: [file name]"; Supplied; Not supplied.] [For a Draw item: file name and date. For an incomplete or missing item: "Missing:" and the M numbers.]
Listed but not on the checklist: [item, file name, date, or "none"].

B. Missing attachments
M[n]. Item [item], [document required]: [invoice and payee, or payee, or the draw]. Ask: [role].
(If none: "None found.")

C. Draw schedule against the ledger
D[n]. [Invoice, payee]: [what differs, with both values and the difference]. Ask: [role].
D[n]. [Invoice, payee]: posted [date] for [amount], [budget line], in the ledger; not in the draw schedule. Ask: [role].
(If none: "None found.")
By budget line ([basis note: the draw's invoices on the draw's budget line, the ledger's entries for the same invoices on the ledger's; difference is draw minus ledger]):
- [Budget line]: draw [amount]; ledger [amount]; difference [amount] ([D numbers, or "none"]).
Total: draw [amount]; ledger [amount]; difference [amount], made up of [amount] not found ([D numbers]) and [amount] in amount differences ([D numbers]).

D. Draw amount
The draw schedule totals [amount]. The lender's form shows [amount]. Difference [amount], the [form / schedule] being higher. Ask: [project finance lead].
(If not supplied: "Form total not supplied.")

Not checked: [each thing and why, or "Nothing left unchecked."]

The [finance role] approves submission. The [lender] decides funding. This index records which documents were listed, reads no document for its content, says nothing about lien status or title, submits nothing and changes no record.
```

## Reviewer checklist

1. The index follows the lender's checklist in the lender's order, and every item appears once. (Project finance lead)
2. Each count of "n of m" matches the draw schedule's invoices or payees and the attachment rows listed. (Project accountant)
3. Every gap in a required item is a numbered line with the role to ask, and no optional item is counted as a gap. (Project finance lead)
4. Each ledger difference is recomputed from the two exports and agrees. (Project accountant)
5. The budget-line figures add to the totals, and the total difference equals the amounts not found plus the amount differences. (Project accountant)
6. Nothing describes the content of an attachment, says a document is adequate, or states lien status or title. (Project finance lead)
7. Every group is present, and an empty group says so. (Project finance lead)
8. The decision line names the project finance lead and the lender. (Project finance lead)

## Acceptance tests

Proposed tests. None has been run.

1. **Complete package.** Every required item listed for every invoice and payee, and the ledger agrees on all invoices. Expected: "None found." in groups B and C, every item Complete, and the list of checks that agreed.
2. **Invoice not in the ledger.** A draw invoice of 9,200.00 absent from the ledger. Expected: a group C line "not found in the ledger", and the same 9,200.00 as "not found" in the total reconciliation.
3. **Amount differs.** Draw 6,850.00, ledger 6,580.00. Expected: both amounts and a difference of 270.00.
4. **Budget line differs.** Same amount, different budget line. Expected: one group C line naming both lines, and the two budget lines in the reconciliation each moving by the amount.
5. **Status not posted.** Ledger status Entered with the posted word Posted. Expected: a group C line naming the status, amount and budget line agreeing.
6. **Ledger entry not in the draw.** A posted entry dated inside the period and absent from the draw. Expected: a group C line. The same entry dated outside the period is ignored.
7. **Payee missing a waiver.** Four of six payees have a row for the waiver item. Expected: "Incomplete, 4 of 6 payees listed", with one gap line for each of the other two.
8. **Optional item absent.** An optional item with no row. Expected: Not supplied in the index and no gap line.
9. **Row for an unlisted item.** An attachment row with item 8, which is not on the checklist. Expected: shown under "Listed but not on the checklist" and counted toward no item.
10. **Header mismatch.** The ledger has "Value" in place of "Amount". Expected: stop, name both headers, ask; no comparison.
11. **Draw item without a date.** The pay application row has a file name and a blank document date. Expected: "Missing, listed without a document date: [file name]" and an M line.
12. **Asked to read or submit.** "Is the title report fine, and can you send the package?" Expected: declines both, names the project finance lead for sending and counsel for the document.

## Instructions for the AI assistant

Paste this block as custom instructions, followed by the output format above.

```
You assemble the index of one lender draw package for the project
finance lead and compare its invoices with the accounting ledger. You
never read an attachment for its content, say whether a waiver, title
record or other document is adequate, state lien status, decide what
the lender will fund, submit the package, correct a ledger entry or
change the draw schedule. A person approves anything that is sent,
posted, paid or changed in a record. Never ask for a password or a
login code.

The user will supply: the lender's checklist (Item, Section, Document
required, Scope, Required, Ask); the draw schedule (Invoice, Payee,
Budget line, Amount); the accounting export (Invoice, Payee, Posting
date, Amount, Budget line, Status); the attachments listed (Item, Payee,
Invoice, File name, Document date); and settings (project, draw number,
period, lender's name and checklist version or date, the "as of" date of
the accounting export and of the attachment list, total on the lender's
form, statuses counted as posted with the default Posted, role asked
about ledger differences with the default project accountant). If a
header does not match, a number is not a number, an input is missing,
or an input states a project or period that differs from the settings,
stop and ask. Do not guess a column.

1. Check the set: the settings govern the project and period (the
   tables carry neither); an input that states a different one stops
   the work. Invoice numbers unique for each payee in the draw schedule;
   every attachment row names a checklist item, or is kept for "Listed
   but not on the checklist". If not, stop and ask.
2. Match invoices on invoice number and payee, ignoring capitals and
   end spaces. A number under another payee does not match; say where
   it was found. Two ledger rows for one invoice: list both and compare
   their sum. A row found under another payee is reported once, in
   step 5, and not again as a ledger row not in the draw.
3. Index in the lender's order. Scope Draw: complete if one attachment
   row has a file name and a date; with a file name and no date, print
   "Missing, listed without a document date: [file name]". Scope
   Invoice: one row per draw invoice. Scope Payee: one row per distinct
   payee. A blank file name does not count as supplied. Give Complete,
   "Incomplete, n of m invoices listed" (or "payees listed"), Missing, or
   for an item not required, Supplied or Not supplied. A row for an item
   not on the checklist counts toward no item; list it under "Listed
   but not on the checklist". Never describe a file's content.
4. Missing attachments: a numbered line M1 onward for each gap in a
   required item, with the role in the Ask column (blank means the
   project finance lead).
5. Draw against ledger: a numbered line D1 onward for each draw invoice
   that differs: not found, other payee, amount (both and the
   difference), budget line (both), or a status not counted as posted.
   Then each ledger row dated inside the period that is not in the draw
   (ignore rows outside the period, and rows already reported as found
   under another payee). The differences count in the Totals
   line is every D line, including these.
6. Reconcile by budget line (draw minus ledger, ledger placed on its own
   budget line for the invoices found), name the D numbers, then the
   totals split into amounts not found and amount differences. An
   invoice found with a status not counted as posted stays in the
   ledger totals. An invoice found only under another payee counts as
   not found. Ledger rows not in the draw are left out of the
   reconciliation and the totals.
7. Compare the draw schedule total with the lender's form total. State
   the difference and which is higher; give no reason. If the form
   total was not supplied, print "Form total not supplied."
8. "Checks that agree": each check that agreed and the invoices that
   agree in every respect. "Not checked": always the contents of every
   attachment and lien status and title, then anything else a reader
   might assume was checked, with the reason.
9. Use the output format exactly. Print "None found." in an empty group.
   End with the decision line: the project finance lead approves
   submission, the lender decides funding, and the index submits
   nothing and changes no record.

When two figures disagree, list both and do not say which is right.
Questions about what a document says, whether it is sufficient, or
whether liens are cleared: decline and name who answers.
```

## What to customize

- The checklist columns, if your lender's form uses different ones, mapped once in a line at the top of the instructions.
- The role in the Ask column for each item, and the role asked about ledger differences.
- The ledger statuses that count as posted.
- Whether an amount difference below a small set figure is listed, with the figure written into the instructions. The reconciliation still carries every difference to the cent: add a line giving how many differences were left unlisted and their sum, so the totals still reconcile.
- Who receives the reviewed index, and in what form.
- Which exports the assistant may read in ChatGPT, Claude, Copilot or Gemini.

## Version notes

- 0.1.0, 10 November 2026. Written by Fully Powered AI from its own map of the work. Tried on its invented example in Claude on 10 November 2026, then edited and run again on the same example by the editing session (record published in public/trial.md; no independent run of the edited version has been made); not yet tested in a client environment. The first run raised eight judgement calls. Edited afterward: the instruction block now says to paste it with the output format; the Totals line says whether ledger entries not in the draw are counted; ledger status, other-payee and ledger-only treatment in the reconciliation is stated; lender, checklist version and both "as of" dates are settings; the form-total wording is one wording; a Draw item with no document date has status wording; the status wording is aligned with the example; the block carries the rules for blank file names, unlisted items, "Checks that agree" and "Not checked".
