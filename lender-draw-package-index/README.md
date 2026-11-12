# Lender draw package index

Before a monthly draw goes to the lender, the project finance lead has an index in the lender’s own order: every required document listed or missing, and every invoice set against the ledger. The lender decides funding; nothing is submitted.

*Workflow template · Construction · Finance and accounting · version 0.1.0 · [Workflows Directory](https://fullypowered.ai/workflows/lender-draw-package-index/)*

## The outcome

The finance lead opens the draw knowing what is in the package and what is not. The index follows the lender’s checklist item by item. Each item reads complete, incomplete or missing, and each gap is a numbered line naming the document, the payee or invoice it concerns and the person to ask.

The draw schedule is also set beside the accounting ledger, invoice by invoice. A cost that is not posted, an amount that differs, a budget line that does not agree and a posted cost that is absent from the draw all appear with their amounts, and the totals are reconciled by budget line.

The index lists and compares. It reads no document for its content, says nothing about lien status or title, and does not decide whether the lender will fund.

## Who starts the work, and when

The project accountant or a finance coordinator starts it when the monthly draw-preparation date arrives, once the month’s costs are posted and the attachments have been gathered. It can run again as gaps are closed, and each run shows what is still open.

The project finance lead reviews the index and decides whether the package is submitted. The lender’s reviewers decide funding. Anyone who needs a legal document reviewed sends it to the people who do that work.

## What they supply

- The lender’s checklist for the draw, with its sections and the scope of each item.
- The draw schedule: each invoice in the draw, its payee, budget line and amount.
- The accounting export for the period.
- A list of the attachments gathered: which checklist item each serves, for which payee or invoice, its file name and its date.
- Settings: the project, the draw number, the period, the total entered on the lender’s form and the ledger statuses that count as posted.

## What comes out

One page in a fixed order. It shows the basis, the checks that agreed, the index in the lender’s order, the missing attachments, the draw schedule against the ledger with a reconciliation by budget line, and the draw amount against the lender’s form. A group with nothing in it says so. A closing line says that the finance lead approves submission and the lender decides funding.

See the worked example with invented data in [EXAMPLE.md](EXAMPLE.md).

## Where it fits

- [Finance and accounting](https://fullypowered.ai/functions/finance-and-accounting/), where the project finance lead owns the draw and its support.
- [Construction](https://fullypowered.ai/industries/construction/), where a monthly draw follows the month’s invoices, the progress billing and the site reports.
- [Real estate](https://fullypowered.ai/industries/real-estate/), for owners and developers who draw on a construction loan and answer to the lender each month.
- [Established businesses](https://fullypowered.ai/situations/established-businesses/), where several projects draw in the same week.
- [Growth & scaling](https://fullypowered.ai/situations/growth-and-scaling/), when the number of draws outgrows a careful hand check of each package.

It stays apart from [pay application line check](https://fullypowered.ai/workflows/pay-application-line-check/), which compares a contractor’s billing with the schedule of values, the changes and the site evidence; here the pay application is only a document that is listed. It also stays apart from [thirteen-week cash flow forecast](https://fullypowered.ai/workflows/thirteen-week-cash-flow-forecast/), which looks ahead at cash, while this index looks at one month’s package.

## What has to change for your company

Put your lender’s checklist in the stated columns, in the lender’s order, and name for each item the role to ask when it is missing. Set the ledger statuses that count as posted and the role asked about ledger differences. Decide who gathers the attachments and who sends the package. Keep legal documents out of the assistant’s hands: it lists that a document was supplied and its date, and a question about what a document says goes to the people who answer it.

## What has been checked

Fully Powered AI wrote this workflow template. It was editorially reviewed on 10 November 2026. It was tried on its invented example in Claude on 10 November 2026, then edited and run again on the same example by the editing session, and the record is published with it. It has not yet been tested in a client environment.

Testing in your environment means running it on two or three past draws the finance lead already knows, with cases written in advance: an invoice missing from the ledger, an amount that differs, a payee with no attachment listed, a ledger entry that is not posted. The finance lead checks every line against the lender’s checklist and the ledger before anyone relies on it. [Pilot acceptance-test preparation](https://fullypowered.ai/workflows/pilot-acceptance-test-preparation/) sets those cases up.

- Written by Fully Powered AI.
- Sources and rights reviewed.
- Editorially reviewed on 10 November 2026.
- Package format checked by script on every release.
- Tried once on its invented example in Claude on 10 November 2026. The record is in [TRIAL.md](TRIAL.md).
- Not yet tested in a client environment.

## What is in this folder

- [TEMPLATE.md](TEMPLATE.md): the complete workflow template. Roles, inputs, the procedure, exceptions and stop conditions, the output format, a reviewer checklist, acceptance tests, the instructions for an AI assistant and what to customize.
- [EXAMPLE.md](EXAMPLE.md): a worked example with invented data.
- [TRIAL.md](TRIAL.md): what came out when the template was tried on its example.
- [SKILL.md](SKILL.md): the technical file, for AI products that load packaged instructions from a folder.
- [SOURCES.md](SOURCES.md): what the workflow template drew on, with licences.
- [LICENSE](LICENSE): MIT. Use it, change it, make it yours.

## Start using it

1. Read [EXAMPLE.md](EXAMPLE.md) to see what a good result looks like.
2. Open [TEMPLATE.md](TEMPLATE.md) and set every item under "What to customize" to your own rules, roles and limits.
3. Give your AI assistant the instruction block and the output format from the template, with your own limits in place of the ones the instructions leave open in square brackets. Paste them in as custom instructions in ChatGPT, Claude, Copilot or Gemini, or copy this whole folder into a product that loads `SKILL.md` packages. This folder stands alone; you do not need the rest of the repository.
4. Run it on past work first, using the reviewer checklist and acceptance tests in the template, before anyone relies on it.

## Related workflow templates

- [Pay application line check](../pay-application-line-check/)
- [Thirteen-week cash flow forecast](https://fullypowered.ai/workflows/thirteen-week-cash-flow-forecast/)
- [Month-end close checklist](https://fullypowered.ai/workflows/month-end-close-checklist/)

## Make it yours

This is the starting version. Fully Powered AI adapts workflow templates to how your company works, proves them on real work and rolls them out to the roles that use them. [Talk with us](https://fullypowered.ai/contact/).
