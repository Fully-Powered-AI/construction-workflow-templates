# AI workflow templates for construction firms

FullyPowered Workflow Templates for construction firms and contractors turn the AI your company already pays for into a team that knows how the work is done: an estimator with the estimate basis worksheet laid out, every gap written as a scope question, a project accountant with each pay application line compared against the schedule of values, a superintendent with the three-week look-ahead set beside everything that could hold it up. 6 workflow templates, made to be customized and deployed. All plain Markdown, all free, MIT license.

We are FullyPowered AI. We build AI workflows for companies, and these are the templates we start from. We publish them because a good starting point should be open to everyone. Copy one. Change it. Make it yours.

> [!TIP]
> **Missing a template that is not listed here, or want these customized for your organization? Reach out to us.** These are templates, made to be customized and deployed. FullyPowered AI customizes and builds AI workflows, connects them to your business systems, installs them in your agents and puts them in the hands of the people who own the work. [See more examples for construction firms and contractors](https://fullypowered.ai/industries/construction/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=construction-readme&from=gh-construction-readme) · [Have one built for your team](https://fullypowered.ai/pricing/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=construction-readme&from=gh-construction-readme) Not sure where to start? Email hello@fullypowered.ai and a person will answer.

**Who this is for**

- Contractors and owners who have paid for AI and want it doing real project work.
- Project managers who want a careful way to run submittals and closeouts this week.
- The estimator or superintendent who gets a precise brief, checks it and still makes the call.

**What these are for**

- **Your best way of doing it, for the whole team.** One piece of work, written down precisely enough that an assistant prepares it the same way every time.
- **Work you can check.** Every template says what it needs, what it produces, what it checked and what it could not.
- **A person decides.** Anything that sends, posts, pays or changes a record waits for someone to approve it.
- **Tied into your business systems.** A workflow can be designed to pull from the systems your company already runs, and even push data back into them, with guardrails and a person approving. [Browse the Connectors Directory](https://fullypowered.ai/connectors/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=construction-readme&from=gh-construction-readme).
- **Free, open and portable.** MIT-licensed plain instructions that run in the assistant or agent your team already uses: ChatGPT, Claude, Claude Code, Claude Cowork, Codex, Copilot, Gemini, Grok, Perplexity.

**Quick start**

1. **Turn walk notes into one punch list.** Open ChatGPT, Claude, Copilot or Gemini. Copy the text below into a new chat. Replace the square brackets with your own punch list, walk notes and contractor updates, or use invented ones to see how it works. Nothing is sent and nothing in your records changes.

   ```text
   You prepare a consolidated punch list for a site manager. You prepare; the site manager decides. Do not assign work, close or reopen items, accept work, judge workmanship or contact anyone. A trade saying work is done is not a verified closure. I will give you: the prior punch list [paste it], my walk notes [paste them], contractor updates [paste them], and settings [project, today's date, walk date, target closeout]. Merge walk notes into existing items only when they name the item or match location, trade and wording exactly. Group the result by location, then trade. Show overdue items, items raised again, items a trade reports complete, possible duplicates, items with no photograph, and a proposed follow-up date for each open item. End with numbered questions for me. If anything is missing or unclear, ask before you start.
   ```

2. Read what comes back. It marks what it checked and what is left for you. What comes out, with invented data:

   ```text
   **PUNCH LIST CONSOLIDATION: the Lakeside Annex, walk of Tuesday 17 November 2026**

   For: the site manager. Prepared Tuesday 17 November 2026 from: prior punch list (6 rows), walk notes (8 rows), contractor updates (4 rows), settings.
   Column check: all headers matched.
   Settings: walk date Tuesday 17 November 2026, follow-up 7 days, next walk not supplied, target closeout Friday 11 December 2026, counted in calendar days. Defaults used: follow-up days.
   Summary: 9 items. Open 7 (overdue 3). Contractor reports complete, awaiting verification 1. Verified closed 1. Raised again at the walk 2. Walk notes 8: merged into existing items 5, new items 3. Contractor updates attached 4. Possible duplicates not merged 1 pair. Items with no photograph 2. Trade not stated 1. Proposed follow-up dates 8 (trade's own date 3, existing due date 0, next walk 0, default 4, verification 1); after target closeout 0.

   **Data checks**

   - U-04 has no item number. It was attached to P-05, the only item with the same location and trade (Level 2 Room 2.02, Trade A).
   ```

3. Stop there. You will know if this is for you. When you want it fitted to your company, or built into your agents, [that is what we do](https://fullypowered.ai/pricing/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=construction-readme&from=gh-construction-readme).

In every workflow a person starts the work, supplies the documents and makes the decision; the template prepares and checks.

These are samples and a starting point, made to be changed to fit how your firm works. Work that is not listed here can still be built, as a single step or as many.

## The workflow templates here today

- **[Estimate basis pack](estimate-basis-pack/)**: An estimator pricing a job from drawings, takeoffs and supplier quotes gets one worksheet: every figure with its quantity source, rate source and date beside it, each exclusion listed and every gap already written as a scope question. The estimator verifies; the bid lead decides the figure.
- **[Lender draw package index](lender-draw-package-index/)**: Before a monthly draw goes to the lender, the project finance lead has an index in the lender’s own order: every required document listed or missing, and every invoice set against the ledger. The lender decides funding; nothing is submitted.
- **[Pay application line check](pay-application-line-check/)**: Before a progress billing goes on, the project accountant has every line compared with the schedule of values, the last certificate, the approved changes and the evidence supplied, with each arithmetic difference listed. The authorized certifier decides payment; nothing is certified.
- **[Punch list consolidation](punch-list-consolidation/)**: The site manager gets the punch list for the next closeout walk as one list grouped by location and trade, with repeated entries merged, photographs attached and a proposed follow-up date for each open item. Nothing is assigned, closed or accepted.
- **[Submittal register review](submittal-register-review/)**: The project engineer gets one register of every required submittal: what has arrived, the review status as recorded, the documents still missing and the long-lead items at risk against the date each order must be placed. Nothing is routed, accepted or ordered.
- **[Three-week look-ahead constraint review](three-week-look-ahead-constraint-review/)**: Before the coordination meeting, the superintendent gets a brief that sets each planned activity of the next three weeks beside what could hold it up: trades sharing an area, unfinished predecessors, open approvals, late deliveries and unanswered RFIs. The superintendent confirms the sequence and assigns the follow-up.

## How to use one

Open a folder and start with its README. Every folder stands alone, so copy the one you want and leave the rest. The templates are written for ChatGPT, Claude, Copilot and Gemini: paste the instruction block and the output format in as custom instructions, or load the folder in a product that reads `SKILL.md` packages.

To take the whole collection, press **Use this template** at the top of this page: it copies every folder into a repository in your own account, yours to change.

In every template a person starts the work, supplies the inputs and decides. The template prepares and checks. Anything that sends, posts, pays or changes a record waits for a person to approve it.

## What SKILL.md is

Each folder holds a file named `SKILL.md`. It is the technical file: the same instructions and output format as the template, in the packaged form that AI products which load instructions from a folder read. It is generated from `TEMPLATE.md`, so the two always agree. The workflow template is the whole folder; `SKILL.md` is one way of loading it. If your AI product does not read that format, use `TEMPLATE.md`.

## What "checked" means here

Each folder says exactly what was checked and when: who wrote it, that its sources and rights were reviewed, the date of its editorial review, and whether it has been tried on its invented example in a named AI product. Nothing is described as tested for a client unless it was. Test a template on your own past work before your team relies on it; each one comes with acceptance tests for that.

## More workflow templates

The [FullyPowered Workflows Directory](https://fullypowered.ai/workflows/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=construction-readme&from=gh-construction-readme) lists every workflow template across functions and industries, with search. A machine-readable list of this repository is in [index.json](index.json).

For the work these templates come from, by area of the business and by task, see [AI workflow examples for construction companies](https://fullypowered.ai/industries/construction/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=construction-readme&from=gh-construction-readme).

## Licence and credits

MIT, in [LICENSE](LICENSE) and in every folder. Each folder's SOURCES.md names what the workflow template drew on. Published by [FullyPowered AI](https://fullypowered.ai/?utm_source=github&utm_medium=referral&utm_campaign=workflow-collections&utm_content=construction-readme&from=gh-construction-readme).
