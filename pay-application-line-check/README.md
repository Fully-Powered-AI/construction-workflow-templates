# Pay application line check

Before a progress billing goes on, the project accountant has every line compared with the schedule of values, the last certificate, the approved changes and the evidence supplied, with each arithmetic difference listed. The authorized certifier decides payment; nothing is certified.

*Workflow template · Construction · Finance and accounting · version 0.1.0 · [Workflows Directory](https://fullypowered.ai/workflows/pay-application-line-check/)*

## The outcome

The accountant opens a pay application already knowing where it disagrees with the project's own records. Each line has been set beside the schedule of values, what the last certificate paid, the changes the log shows as approved and the progress evidence that came with it. Every difference is on one page with its amount, the line it sits on and the person to ask.

The things that usually surface late are in front of you on day one: a line total that does not add, a previous-billed figure that is not what was certified, an approved change missing from the application, a change still pending that has been billed, stored materials with no delivery record behind them, a percentage well above what the inspection showed.

The check lists differences. It does not say which figure is right, restate the amount due or approve anything.

## Who starts the work, and when

The project accountant, or the project manager where there is no accountant on the project, starts it when a monthly pay application arrives for review. It can run again on a corrected application, and the new run shows what is still different.

The accountant verifies the figures against the documents. The authorized certifier, whoever the project's own arrangements name, decides payment and whether completion is accepted.

## What they supply

- The pay application: its line schedule, its totals and the amount due it states.
- The schedule of values the project started with.
- The change log, with each change's amount, status and the line it affects.
- The prior certificate: what was certified to date on each line.
- The progress evidence: inspection records, the superintendent's log and delivery records for stored materials.
- Three settings: how far a percentage may differ from the evidence before it is listed, the retainage rate if it is to be checked, and which status words in the change log count as approved.

## What comes out

One page in a fixed order. It shows the basis, which checks agreed and then the differences in six groups: arithmetic on the page, previous billing, changes, progress evidence, stored materials, and retainage and amount due. Each difference has its amount, a note where one difference causes another, and the role to ask. A closing line gives the amount due as the application states it and says the comparison restates nothing.

Anything that could not be checked is listed with the reason. A group with nothing in it says so.

See the worked example with invented data in [EXAMPLE.md](EXAMPLE.md).

## Where it fits

- [Finance and accounting](https://fullypowered.ai/functions/finance-and-accounting/), where the project accountant owns the review before payment is certified.
- [Construction](https://fullypowered.ai/industries/construction/), where monthly billing runs against a schedule of values, approved changes and site evidence.
- [Real estate](https://fullypowered.ai/industries/real-estate/), for owners and developers who review contractors' applications on their projects.
- [Established businesses](https://fullypowered.ai/situations/established-businesses/), where several projects are billing at once and one accountant checks them all.
- [Growth & scaling](https://fullypowered.ai/situations/growth-and-scaling/), when the number of applications outgrows a careful read of each one.

It stays apart from [client billing summary](https://fullypowered.ai/workflows/client-billing-summary/), which prepares an outgoing invoice for a client to read, and from review of time-and-expense entries before billing. This workflow template checks a progress billing the reviewer has received.

## What has to change for your company

Put your own column names in the stated places, or tell the assistant how your forms map to them. Set the tolerance for evidence, the retainage rate and base the accountant works from, and the status words your change log uses for approved. Decide who is asked about each kind of difference: the contractor's billing contact, the project manager, the superintendent. Name the certifier role your projects use. Keep the contract itself out of the assistant's hands: questions about what a clause means go to the people who answer them.

## What has been checked

Fully Powered AI wrote this workflow template. It was editorially reviewed on 10 November 2026. It was tried on its invented example in Claude on 10 November 2026; the record is published with it. The points that run found open were settled the same day, after an independent review, without a rerun; the record lists them and says where the recorded output differs from the template as it now stands. It has not yet been tested in a client environment.

Testing in your environment means running it on two or three past applications the accountant already knows well, with cases written in advance: a total that does not add, a billed change that was never approved, stored materials with no receipt, an evidence percentage below the claim. The accountant checks every figure against the documents before anyone relies on it. [Pilot acceptance-test preparation](https://fullypowered.ai/workflows/pilot-acceptance-test-preparation/) sets those cases up.

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

- [Client billing summary](https://fullypowered.ai/workflows/client-billing-summary/)
- [Supplier bill review and payment-run preparation](https://fullypowered.ai/workflows/supplier-bill-review-and-payment-run-preparation/)
- [Scope change impact review](https://fullypowered.ai/workflows/scope-change-impact-review/)
- [Lender draw package index](../lender-draw-package-index/)

## Make it yours

This is the starting version. Fully Powered AI adapts workflow templates to how your company works, proves them on real work and rolls them out to the roles that use them. [Talk with us](https://fullypowered.ai/contact/).
