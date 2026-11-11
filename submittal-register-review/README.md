# Submittal register review

The project engineer gets one register of every required submittal: what has arrived, the review status as recorded, the documents still missing and the long-lead items at risk against the date each order must be placed. Nothing is routed, accepted or ordered.

*Capability template · Construction · Project and delivery · version 0.1.0 · [Capabilities Directory](https://fullypowered.ai/capabilities/submittal-register-review/)*

## The outcome

A submittal log tells you what was filed. It rarely tells you what is missing, what has sat unrouted for two weeks, or which equipment will miss its order date if review runs its usual length. This capability turns the specification's list of required submittals, the log of packages received and purchasing's order dates into one register in submittal-number order.

Each line shows the latest package, the status exactly as the log records it, and whether every required document came with it. Four short lists follow: documents still missing, packages whose routing needs checking, long-lead items not yet accepted, and anything that cannot clear review in the time left before its order date. Reviewer comments are printed word for word and never read as approval.

## Who starts the work, and when

The project engineer, or the project coordinator working for them, runs it when a submittal arrives, before the weekly procurement or coordination meeting, and whenever a material release is coming up. It can be rerun whenever the log changes.

## What they supply

- The required-submittals list taken from the specifications: number, section, description, trade and required documents.
- The submittal log: each package received, its revision, documents, routing and recorded status.
- Purchasing's dates: the date each order must be placed and its lead time in days.
- Today's date, the review period your project allows, and the long-lead threshold you use.

## What comes out

A dated register with a summary count, then the missing-documents, routing, long-lead and at-risk lists, and a numbered set of questions for the project engineer. Each question gives the facts first and recommends nothing. Where a section is empty it says so.

See the worked example with invented data in [EXAMPLE.md](EXAMPLE.md).

## Where it fits

- [Construction](https://fullypowered.ai/industries/construction/), where equipment and finishes are bought months before they are installed.
- [Engineering firms](https://fullypowered.ai/industries/engineering-firms/), where the design side tracks what has been reviewed and what is still outstanding.
- [Real estate](https://fullypowered.ai/industries/real-estate/), for owners and developers following a project's long-lead items.
- [Project and delivery](https://fullypowered.ai/functions/project-and-delivery/), which owns the schedule the order dates protect.
- [Quality management](https://fullypowered.ai/functions/quality-management/), which wants a clean record of what was reviewed and when.
- [Procurement and suppliers](https://fullypowered.ai/functions/procurement-and-suppliers/), who need to know which orders are waiting on a review.
- [Established businesses](https://fullypowered.ai/situations/established-businesses/), with a standing submittal log and a routine for it.
- [Growth and scaling](https://fullypowered.ai/situations/growth-and-scaling/), when one project engineer now carries more projects than before.

## What has to change for your company

Use your own status words and decide which of them count as accepted. Set the review period in the contract, the extra days a resubmission takes, and the lead time you treat as long. Decide who verifies routing and how late a package may sit with a reviewer before it is listed. Agree the document names so the required list and the log match exactly. This capability reviews no technical content and certifies no compliance with the specifications; the authorized design reviewer decides each submittal.

## What has been checked

Fully Powered AI wrote this capability template in its own words from its own map of the work, with no third-party text. It was editorially reviewed on 10 November 2026. It was tried once on its invented example in Claude on 10 November 2026; the record is published with it. The example's own output was visible during that run, so it was not a blind run. Small edits made afterward to the example, the question wording and the instructions, including clauses on a reviewer comment that disagrees with the status, a package logged with no documents and an unreadable date, have not been run again; the template's version notes list them. It has not yet been tested in a client environment. It has not yet been tested as a packaged version in ChatGPT, Claude, Copilot or Gemini.

Testing on your project means running it on a log your project engineer already knows well, with cases written in advance: a package with a missing document, one that was never routed, a long-lead item with no time left. The project engineer checks every date and count against the log before anyone relies on the register.

- Written by Fully Powered AI.
- Sources and rights reviewed.
- Editorially reviewed on 10 November 2026.
- Package format checked by script on every release.
- Tried once on its invented example in Claude on 10 November 2026. The record is in [TRIAL.md](TRIAL.md).
- Not yet tested in a client environment.

## What is in this folder

- [TEMPLATE.md](TEMPLATE.md): the complete capability template. Roles, inputs, the procedure, exceptions and stop conditions, the output format, a reviewer checklist, acceptance tests, the instructions for an AI assistant and what to customize.
- [EXAMPLE.md](EXAMPLE.md): a worked example with invented data.
- [TRIAL.md](TRIAL.md): what came out when the template was tried on its example.
- [SKILL.md](SKILL.md): the technical file, for AI products that load packaged instructions from a folder.
- [SOURCES.md](SOURCES.md): what the capability drew on, with licences.
- [LICENSE](LICENSE): MIT. Use it, change it, make it yours.

## Start using it

1. Read [EXAMPLE.md](EXAMPLE.md) to see what a good result looks like.
2. Open [TEMPLATE.md](TEMPLATE.md) and set every item under "What to customize" to your own rules, roles and limits.
3. Give your AI assistant the instruction block and the output format from the template, with your own limits in place of the ones the instructions leave open in square brackets. Paste them in as custom instructions in ChatGPT, Claude, Copilot or Gemini, or copy this whole folder into a product that loads `SKILL.md` packages. This folder stands alone; you do not need the rest of the repository.
4. Run it on past work first, using the reviewer checklist and acceptance tests in the template, before anyone relies on it.

## Related capabilities

- [Supplier delivery date check](https://fullypowered.ai/capabilities/supplier-delivery-date-check/)
- [Vendor renewal review](https://fullypowered.ai/capabilities/vendor-renewal-review/)
- [Reviewer comments into one resolution list](https://fullypowered.ai/capabilities/reviewer-comments-resolution-list/)

## Make it yours

This is the starting version. Fully Powered AI adapts capabilities to how your company works, proves them on real work and rolls them out to the roles that use them. [Talk with us](https://fullypowered.ai/contact/).
