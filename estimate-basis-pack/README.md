# Estimate basis pack

An estimator pricing a job from drawings, takeoffs and supplier quotes gets one worksheet: every figure with its quantity source, rate source and date beside it, each exclusion listed and every gap already written as a scope question. The estimator verifies; the bid lead decides the figure.

*Workflow template · Construction · Sales · version 0.1.0 · [Workflows Directory](https://fullypowered.ai/workflows/estimate-basis-pack/)*

## The outcome

The figure a bid lead submits stands on a page that shows what it rests on. Beside each amount sit the quantity and where it came from, the rate and whose quote or price book it is, the date of that rate, and any reason to doubt either. Lines priced on a drawing revision that has since been replaced, a quote past its valid-to date or an assumed quantity are marked where they stand, not discovered at the bid meeting.

What the price leaves out is written down too: each exclusion, whose it is and which lines it touches. What nobody can price yet becomes a numbered scope question for a named role.

The estimator still does the estimating. The workflow template does no takeoff, sets no rate and chooses no quote. It never fills a blank with a guess; a line with no quantity or no rate shows no figure and says why.

## Who starts the work, and when

The estimator starts it when a drawing set or a scope revision needs pricing, and again when a new revision, a refreshed quote or an addendum arrives. The bid lead reads the result before deciding the figure to submit.

## What they supply

- **The drawing register:** each sheet, its current revision and its date.
- **The takeoff export:** each line with its unit, quantity, where the quantity came from and the sheet and revision it was taken from.
- **The rates:** a rate for each line, with its source, reference and date.
- **The quotes list:** each supplier quote with its dates, the drawings it priced and what it includes and leaves out.
- **Your settings and notes:** the pricing date, the bid due date, your standing exclusions, how old a price-book rate may be, and notes such as addenda.

## What comes out

One worksheet in a fixed order: the basis checks, every line with its basis and flags, the exclusions, the open scope questions, totals that separate figures resting on a clean basis from figures resting on a flagged one, what the estimator must verify and the decisions that belong to the bid lead.

Overhead, profit, contingency and tax are not in it. They are the bid lead's, and the page says so.

See the worked example with invented data in [EXAMPLE.md](EXAMPLE.md).

## Where it fits

- [Finance and accounting](https://fullypowered.ai/functions/finance-and-accounting/), where the figure behind a bid has to be explainable line by line.
- [Procurement and suppliers](https://fullypowered.ai/functions/procurement-and-suppliers/), where supplier quotes arrive with their own inclusions, exclusions and expiry dates.
- [Sales](https://fullypowered.ai/functions/sales/), where a proposal or bid needs the figure behind its price explained line by line.
- [Construction](https://fullypowered.ai/industries/construction/), where each drawing revision and addendum can change a quantity after it was priced.
- [Engineering firms](https://fullypowered.ai/industries/engineering-firms/), where fee and works estimates are built from drawings and rate sources.
- [Manufacturing](https://fullypowered.ai/industries/manufacturing/), where custom work is priced from drawings and supplier quotes.
- [Established businesses](https://fullypowered.ai/situations/established-businesses/), where the estimating conventions live in one senior person's head.
- [Growth & scaling](https://fullypowered.ai/situations/growth-and-scaling/), when more bids arrive than the estimator can document one by one.

## What has to change for your company

Fix the columns your takeoff and rates exports use, or map them to the defaults. Decide how old a price-book or historical rate may be before it is flagged. List the exclusions your company always carries. Say which sources count as a rate (a supplier quote, a price book, a past job, an allowance) and which of them you accept without a quote. Agree who answers each kind of scope question. Decide what the bid lead adds on top of the worksheet and where the pack is kept. It runs in ChatGPT, Claude, Copilot or Gemini from files you supply; it needs no connection to your estimating software.

## What has been checked

Fully Powered AI wrote this workflow template. It was editorially reviewed on 10 November 2026. It was tried on its invented example on 10 November 2026 in Claude; the record is published with it, and covers the revised version only for the cases that example contains (a superseded drawing, an expired quote, a quote on an older revision, a blank quantity, a missing rate, an assumed quantity, an allowance, an old rate and a quote that supplies only). Rules for unreadable values, unit mismatches, rates with no line, differing valid-to dates, a line covered twice, a quote not supplied, a drawing not in the register, the header and repeated-id stops and missing files have not been run. It has not yet been tested in a client environment. It has not yet been tested as a packaged version in ChatGPT, Claude, Copilot or Gemini.

Testing in your environment means running it on two or three bids your estimator already knows, with cases written in advance: a superseded drawing revision, an expired quote, a line with no rate, a quantity that was assumed. The estimator checks every figure against the takeoff and its rate source before anyone relies on it. [Pilot acceptance-test preparation](https://fullypowered.ai/workflows/pilot-acceptance-test-preparation/) sets those cases up, and [what we test before we call an AI workflow ready](https://fullypowered.ai/insights/what-we-test-before-a-workflow-is-ready/) describes the record we keep.

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

- [Vendor quote comparison](https://fullypowered.ai/workflows/vendor-quote-comparison/)
- [Scope change impact review](https://fullypowered.ai/workflows/scope-change-impact-review/)
- [Bid or no-bid and RFP response plan](https://fullypowered.ai/workflows/bid-or-no-bid-and-rfp-response-plan/)

## Make it yours

This is the starting version. Fully Powered AI adapts workflow templates to how your company works, proves them on real work and rolls them out to the roles that use them. [Talk with us](https://fullypowered.ai/contact/).
