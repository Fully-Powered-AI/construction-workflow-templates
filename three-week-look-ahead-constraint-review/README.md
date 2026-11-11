# Three-week look-ahead constraint review

Before the coordination meeting, the superintendent gets a brief that sets each planned activity of the next three weeks beside what could hold it up: trades sharing an area, unfinished predecessors, open approvals, late deliveries and unanswered RFIs. The superintendent confirms the sequence and assigns the follow-up.

*Capability template · Construction · Project and delivery · version 0.1.0 · [Capabilities Directory](https://fullypowered.ai/capabilities/three-week-look-ahead-constraint-review/)*

## The outcome

The coordination meeting starts from one page instead of five logs. Every activity that begins in the next three weeks is listed in the order it starts, and under each is what stands between it and its start date: the work it waits on that is not finished, the dates its trade reports against the dates in the schedule, the approvals and RFIs still open, the delivery that has no promised date.

The review is plain about what is not known. An activity with no update from its trade, or an update more than a week old, is shown as unconfirmed, not assumed to be on track. Two trades that claim the same area at the same time are shown as a conflict, with both claims and the days they share. A closed day on the calendar is skipped in every count of days.

The questions at the end are written for the superintendent: the facts, what waits on the activity, and what has to be settled. The review changes no date, contacts nobody and offers no view on safety or design. Those calls stay with the people accountable for them.

## Who starts the work, and when

The project engineer, project coordinator or field administrator who keeps the logs starts it two or three working days before the coordination meeting, once the trades have sent their latest dates, and runs it again on the morning of the meeting if something has changed. The superintendent reads it, settles the questions and decides what goes to the trades.

## What they supply

- **The settings:** the check date, the meeting date, the working days and the days the site is closed.
- **The approved schedule,** exported with each activity's trade, location, dates, predecessors and status.
- **The trade updates:** what each trade last said about its start, finish and crew.
- **The delivery list,** with the date each item is needed, the date promised and where the order stands.
- **The RFI log and the approvals and submittals log.**
- **The access claims,** where the project keeps them: which trade needs which area, on which days, alone or shared.

Each list has set column headings. If a heading does not match, the assistant stops and asks rather than guessing.

## What comes out

One brief. It opens with a count of the activities and items that need chasing. Then come the activities grouped by the week they start, each with its constraints in plain facts, followed by the trade overlaps, the open approvals, the deliveries to chase and the open RFIs, each with a blank space for the superintendent to name who follows up. Next are numbered questions for the superintendent, and a note of anything supplied that matched no activity. It ends with a blank decision box.

See the worked example with invented data in [EXAMPLE.md](EXAMPLE.md).

## Where it fits

- [Project and delivery](https://fullypowered.ai/functions/project-and-delivery/), which owns the plan for the next stretch of work and the meeting that keeps it honest.
- [Procurement and suppliers](https://fullypowered.ai/functions/procurement-and-suppliers/), whose delivery dates decide whether a trade can start on the day planned.
- [Construction](https://fullypowered.ai/industries/construction/), where the superintendent walks into each coordination meeting with several trades wanting the same space.
- [Engineering firms](https://fullypowered.ai/industries/engineering-firms/), where the firm coordinates a contractor's look-ahead on a project it designed.
- [Real estate](https://fullypowered.ai/industries/real-estate/), where the owner's team builds out or renovates space and needs to see what could delay a handover.
- [Established businesses](https://fullypowered.ai/situations/established-businesses/), where the look-ahead lives in a superintendent's notebook and should live in a brief that anyone can read.

## What has to change for your company

Map your scheduling product's export to the column headings once and keep the mapping with the template. Decide the length of the window and how old a trade update may be before it counts as stale. Use one spelling for each area in the schedule and the access claims, because overlaps are found by matching those names. Decide which items your project tracks in the approvals log and the statuses your logs use. Name who receives the approved brief and where the signed decision is kept. It runs in ChatGPT, Claude, Copilot or Gemini from files you supply, with no connection to your scheduling or document systems.

## What has been checked

Fully Powered AI wrote this capability template from its own published map of the work. It was editorially reviewed on 10 November 2026. It was tried on its invented example on 10 November 2026 in one run; the record is published with it, and lists the small edits made afterward that have not been run again. It has not yet been tested in a client environment.

Testing in your environment means running it on two or three past look-aheads your superintendent remembers well, plus hard cases written in advance, each with its expected result: a predecessor past its finish, a closed day inside a delivery's lateness, two exclusive claims for one area, an update that is eight days old, an RFI needed after the activity starts. The superintendent checks every date and every count before anyone relies on the brief. [Schedule recovery options](https://fullypowered.ai/capabilities/schedule-recovery-options/) is the next step when a committed date has already slipped, and [Project status report](https://fullypowered.ai/capabilities/project-status-report/) carries the picture to the owner.

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

- [Schedule recovery options](https://fullypowered.ai/capabilities/schedule-recovery-options/)
- [Project status report](https://fullypowered.ai/capabilities/project-status-report/)
- [Supplier delivery date check](https://fullypowered.ai/capabilities/supplier-delivery-date-check/)

## Make it yours

This is the starting version. Fully Powered AI adapts capabilities to how your company works, proves them on real work and rolls them out to the roles that use them. [Talk with us](https://fullypowered.ai/contact/).
