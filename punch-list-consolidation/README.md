# Punch list consolidation

The site manager gets the punch list for the next closeout walk as one list grouped by location and trade, with repeated entries merged, photographs attached and a proposed follow-up date for each open item. Nothing is assigned, closed or accepted.

*Workflow template · Construction · Project and delivery · version 0.1.0 · [Workflows Directory](https://fullypowered.ai/workflows/punch-list-consolidation/)*

## The outcome

After a closeout walk the list is usually three lists: last week's punch list, the notes and photographs from today, and the messages trades have sent since. The same defect appears in all three, a trade's "done" sits beside an item nobody has checked, and nobody can say which items are late. This workflow template turns the three into one list in a fixed order: by location, then by trade.

Each item shows where it came from, the photographs that go with it, any note from the trade word for word, and a date proposed for the next check. Matching is cautious. Entries are merged only when they plainly say the same thing; anything that merely looks alike is shown as a possible duplicate for a person to settle. A trade saying the work is finished is shown as exactly that, and never as a closed item.

## Who starts the work, and when

The site manager, or the site coordinator working for them, runs it once the walk notes are typed up and before the list goes out to the trades. It can be run again after each walk and whenever the trades send updates.

## What they supply

- The prior punch list: each item with its location, trade, description, status as recorded, due date and who verified any closure.
- The walk notes: one row for each observation, with location, trade, wording and a photograph file name where there is one.
- The contractor updates received since the last walk, with any date a trade has promised and whether it says the work is done.
- Typed settings: the project, today's date, the walk date and who decides. Optional: the days to allow before a check, the next walk date and the target closeout date.

## What comes out

A dated, consolidated list with a summary count, then separate lists of possible duplicates, items raised again, items a trade reports complete, overdue items and items with no photograph, and numbered questions for the site manager. Each question gives the facts first and recommends nothing. Where a section is empty it says so.

See the worked example with invented data in [EXAMPLE.md](EXAMPLE.md).

## Where it fits

- [Construction](https://fullypowered.ai/industries/construction/), where the last weeks of a project are won or lost on how fast the remaining items are found, assigned and checked.
- [Real estate](https://fullypowered.ai/industries/real-estate/), for owners and their representatives following a building toward handover.
- [Engineering firms](https://fullypowered.ai/industries/engineering-firms/), for design and site teams that record observations on a walk.
- [Project and delivery](https://fullypowered.ai/functions/project-and-delivery/), which owns the closeout date the list is working toward.
- [Quality management](https://fullypowered.ai/functions/quality-management/), which wants a clean record of what was seen, what was fixed and what was verified.
- [Operations and process improvement](https://fullypowered.ai/functions/operations-and-process-improvement/), for the routine of walk, list and follow-up.
- [Established businesses](https://fullypowered.ai/situations/established-businesses/), with a standing way of running closeout walks.
- [Growth and scaling](https://fullypowered.ai/situations/growth-and-scaling/), when one site manager now closes out more buildings than before.

## What has to change for your company

Use your own status words and decide which ones mean verified closure. Set the days you normally allow before an item is checked and agree who verifies: the authorized inspector, the owner representative or both. Agree the naming of locations and trades, because items are matched on them exactly; the cleaner the names, the fewer possible duplicates. This workflow template assesses no workmanship, judges nothing as safe or compliant, and accepts no work. The site manager assigns, and the authorized inspector or owner representative accepts.

For related work, see [project handover readiness check](https://fullypowered.ai/workflows/project-handover-readiness-check/) for the documents and training that go with a handover, and [safety walk follow-up](https://fullypowered.ai/workflows/safety-walk-follow-up/) for concerns about safety. Neither is covered here.

## What has been checked

Fully Powered AI wrote this workflow template in its own words from its own map of the work, with no third-party text. It was editorially reviewed on 10 November 2026. It was tried once on its invented example in Claude on 10 November 2026, and the record is published with it. Small edits made to the template and the example after that run were not run again; the record lists them. It has not yet been tested in a client environment.

Testing on your project means running it on a punch list your site manager already knows well, with cases written in advance: a repeated entry, an item raised again after it was closed, a trade that says it is finished. The site manager checks every merge, date and count against the source files before the list goes to anyone. The check for wording about danger matches only the words "unsafe", "hazard" and "danger", so a note such as a loose handrail is not flagged by it; add your own company's words to the check, and take anything about safety through the project's safety process.

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

- [Project handover readiness check](https://fullypowered.ai/workflows/project-handover-readiness-check/)
- [Safety walk follow-up](https://fullypowered.ai/workflows/safety-walk-follow-up/)
- [Submittal register review](../submittal-register-review/)

## Make it yours

This is the starting version. Fully Powered AI adapts workflow templates to how your company works, proves them on real work and rolls them out to the roles that use them. [Talk with us](https://fullypowered.ai/contact/).
