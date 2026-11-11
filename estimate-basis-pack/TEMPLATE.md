# Estimate basis pack

Capability template, version 0.1.0.

## Purpose

Prepare the worksheet an estimator and a bid lead price from: every figure built only from a supplied quantity and a supplied rate, with the quantity's source, the rate's source and date, the drawing revision and any reason for doubt written beside it. The worksheet also lists the exclusions and turns every gap into a numbered scope question for a named role. The assistant prepares and checks. It sets no price, performs no takeoff, makes no engineering judgment, chooses no quote and sends nothing. The estimator verifies quantities and prices; the bid lead decides the figure to submit.

## When to use it and when not to

Use it when a drawing set or a scope revision needs pricing, and again whenever a new revision, a refreshed quote or an addendum arrives before the bid is due.

Do not use it:

- To measure quantities from drawings, or to judge whether a design works. The takeoff and every technical judgment stay with the estimator and the designers.
- To compare or choose between supplier quotes. Vendor quote comparison does that; this worksheet only records which quote a rate came from.
- To write the proposal or the bid narrative. Sales proposal preparation does that.
- When the drawing register or the takeoff export is missing, or the export's columns do not match.

## Roles

- **Runs it and verifies it:** the estimator.
- **Reads it and decides the figure to submit:** the bid lead.
- **Answers the scope questions:** the role named on each question, taken from the inputs (the estimator, the bid lead or a role in the takeoff_by column). Where the inputs name none, the bid lead names one; if your settings name a designer, a purchasing lead or a supplier's representative, the assistant can use them. The assistant contacts no one; the estimator or bid lead sends any question.
- **Supplies rates and quotes:** the purchasing lead or the estimator, from the company's own records.

## Inputs

Five inputs. Column headers must match the defaults below exactly (case ignored). If a header is missing, renamed or extra, stop and tell the estimator which header differs; never guess the mapping. The estimator may supply a mapping, such as "our column 'Qty' is quantity", and the assistant then states the mapping at the top of the pack.

1. **Drawing register.** Default headers: `sheet,title,revision,date,status`. One row per sheet in the current set. If missing, stop: revisions cannot be checked.
2. **Takeoff export.** Default headers: `section,item_id,description,unit,quantity,quantity_source,drawing_ref,revision,takeoff_by`. `quantity_source` is one of measured, counted, derived or assumed (any other word is listed as written and flagged "assumed quantity", with the word shown, for the estimator to classify). Quantity may be blank. If missing, stop.
3. **Rates.** Default headers: `item_id,rate,rate_unit,rate_source,source_ref,source_date,valid_until`. `rate_source` is one of supplier quote, price book, historical, allowance. For a supplier quote, `source_ref` is a quote id from the quotes list. `valid_until` may be blank except on quotes. A line with no row has no rate. If the file is missing, treat every line as having no rate and say so.
4. **Quotes list.** Default headers: `quote_id,supplier,quote_date,valid_until,drawings_priced,covers_items,inclusions,exclusions`. `drawings_priced` lists sheet and revision pairs such as "A-501 B"; `covers_items` lists item ids separated by semicolons. If missing, say "quotes list not supplied" and flag every quote-sourced rate.
5. **Settings and notes**, typed by the estimator:
   - Job name, pricing date, bid due date and time, estimator, bid lead.
   - The rate age limit, in days, for price-book and historical rates. Default: 90.
   - Standing exclusions the company always carries.
   - Notes: addenda, scope clarifications, anything the drawings do not show. Notes are treated as the only authority on scope beyond the drawings; nothing is added from general knowledge.

Item ids must be unique in the takeoff. Money is in one currency, stated in the settings.

## The procedure

1. **Check the headers and the files.** Compare each file's headers with the defaults. Stop on any mismatch. Stop if an item id repeats in the takeoff, naming it.
2. **Check the basis.** For each takeoff line, compare `drawing_ref` and `revision` with the register. Flag "drawing not in register" if the sheet is absent, and "superseded drawing" if the revision differs from the register's current one. For each quote, compare `drawings_priced` with the register and flag "quote on superseded drawing" for any pair that differs. Flag "expired quote" when the quote's `valid_until` is earlier than the pricing date; a quote valid to the pricing date is still valid. The quotes list governs the date of a quote; a rate row's own `valid_until` never decides expiry. Count each of these for the "Basis checked" line.
3. **Build each line.** In takeoff order, grouped by `section`. Take quantity, unit and quantity source from the takeoff, and the rate row with the same item id. Amount = quantity × rate, rounded to two decimals (half rounds up), and only when:
   - the quantity is present and the rate row exists, and
   - the takeoff unit equals `rate_unit`.

   Otherwise print "no figure" and flag why: "no quantity", "no rate" or "unit mismatch" (stating both units). Never fill a blank, convert a unit or carry a rate from a similar line.
4. **Flag each line.** In addition to the checks in step 2, flag:
   - "assumed quantity" when the quantity source is assumed or anything other than measured, counted or derived (for any word other than "assumed", show the word as written);
   - "allowance" when the rate source is allowance;
   - "old rate" when a price-book or historical rate's date is more than the rate age limit in the settings days before the pricing date, stating the days;
   - "quote not supplied" when a quote-sourced rate names a quote id that is not in the quotes list;
   - "covered twice" when two quotes both list the same item id;
   - "valid-to dates differ" when a quote-sourced rate row's `valid_until` is filled in and differs from its quote's, stating both dates.

   A line may carry several flags. A line with no flag says "none". A flag never changes the amount.
5. **List the exclusions.** One entry for each of: the company's standing exclusions, every item in a quote's exclusions field, and any limit its inclusions field states (such as "supply only", written as what it leaves out). Give each its source (company standing exclusion, or quote id and supplier) and the lines it applies to (all lines for standing exclusions). Where the exclusion's wording also appears in a takeoff description or a note, say which line, and whether another quote prices that line.
6. **Raise scope questions.** One numbered question for each cause below that applies, naming the lines and the fact with its source. Each distinct fact is its own cause: lines share one question only when they share the same cause and the same fact (the same quote, the same sheet and revision, the same note), and lines with different facts get separate questions even under one bullet below. One line with several causes gets one question for each, so the doors in the example below raise three. A line's missing quantity and its unclassified quantity source are one fact about the quantity and get one question. Causes, in this order:
   - a missing, unreadable or assumed quantity;
   - a missing or unreadable rate;
   - a rate that is an allowance;
   - a superseded drawing or a drawing not in the register, or a quote on a superseded drawing;
   - an expired quote;
   - an exclusion, or limit on inclusions, that disagrees with a note or a line description about what a line includes (for example a quote that supplies only, where a note says the item is supplied and fitted);
   - a line covered twice;
   - an old rate;
   - a unit mismatch;
   - a quote not supplied;
   - a rate with no line;
   - rate dates that differ.

   Order the questions by the first line each concerns, and for the same line in the order of the causes above. Name the role that can answer: use only roles named in the inputs (the estimator and bid lead in the settings, or a role in the takeoff_by column), and if none fits write "role to be named by the bid lead". A question about a line's quantity goes to the role in that line's takeoff_by column. Do not propose an answer.
7. **Total.** Sum the rounded line amounts that have a figure. Report the figured-line total, how much of it sits on lines with no flag, how much on lines with one or more flags, and the count and ids of lines with no figure. Unflagged plus flagged must equal the figured total; if not, stop and recheck the sums. State that overhead, profit, contingency, tax and bonds are not included.
8. **To verify and decisions.** For the estimator: every figured line needs its quantity checked against the drawings and its rate against its source; list the flagged lines first, then the lines with no figure. For the bid lead: write each decision that belongs to the bid lead as a question with its facts: whether to submit with flagged lines as they stand or wait for the refreshed inputs before the due date, how lines with no figure are carried, and whether allowances stand. Recommend nothing unless the bid lead asks.
9. **Trace line and return.** Name the inputs behind every figure and return the pack to the estimator only.

## Exceptions and stop conditions

- **Header mismatch, missing register or missing takeoff:** stop and say exactly what differs or is missing.
- **Repeated item id in the takeoff:** stop and name it.
- **Rate row with no matching takeoff line:** list it under Open scope questions as "rate with no line" (a question as above), and leave it out of the totals.
- **Negative or non-numeric quantity or rate:** treat the line as having no figure, flag "unreadable quantity" or "unreadable rate", and quote the value as supplied.
- **Sums do not agree:** stop; never adjust a figure to make them agree.
- **Asked to measure from a drawing, set or change a rate, pick between quotes, add markup or contingency, write the bid, estimate the effect of a design change, or send a question to anyone:** decline. The estimator or bid lead does it.

## Output format

```
ESTIMATE BASIS PACK: [job name]

For: [estimator as named in the settings], [bid lead as named in the settings]. Pricing date [weekday date]. Bid due [weekday date, time]. Drawing set: [sheets and current revisions].

Basis checked: [n] sheets in the register. [n] takeoff lines. [n] rates. [n] quotes. Takeoff lines on a superseded drawing: [line ids, or none]. Quotes past their valid-to date: [quote ids, or none]. Quotes priced on a superseded drawing: [quote ids, or none].

Worksheet:

[Section name]
[Line id] [Description]. Quantity [quantity unit] ([quantity source]; [sheet] rev [revision]). Rate [rate]/[rate unit] ([rate source], [reference], dated [date], valid to [date or "no valid-to date"]). Amount [amount]. Flags: [flags, or none].
[Line id] [Description]. Quantity [quantity unit, or "not given"] ([quantity source]; [sheet] rev [revision]). Rate [as above, or "none supplied"]. Amount: no figure. Flags: [flags].

Exclusions: [n]
- [Exclusion]. Source: [company standing exclusion, or quote id and supplier]. Applies to: [line ids, or all lines]. [Wording match and whether another quote prices that line, if any.]

Open scope questions: [n]
1. [Line ids]: [fact and its source]. Question: [what must be settled]. Answered by: [role].

Totals:
Figured lines: [n], [total]. On lines with no flag: [amount]. On lines with a flag: [amount]. Lines with no figure: [n] ([line ids]).
Not included: overhead, profit, contingency, tax, bonds and anything else [the bid lead] adds.

To verify, estimator: [all figured lines against the drawings and the rate sources; flagged lines first: ids; lines with no figure: ids]

Decisions for the bid lead: [n]
1. [Question, with its facts.]

Every figure traces to the takeoff export, the rates export, the quotes list and the drawing register supplied for [job name]. The pack sets no price, changes no record and sends nothing.
```

An empty section prints its heading with "None." in place of entries (and a count of 0).

## Reviewer checklist

1. Every amount equals quantity × rate for that line, to two decimals. (Estimator)
2. Every quantity and unit matches the takeoff export, and every rate matches the rates export. (Estimator)
3. Every flag is justified by the register, the quotes list, the settings or the dates, and no flag is missing. (Estimator)
4. Flagged plus unflagged equals the figured total, and the count of lines with no figure is right. (Estimator)
5. Every exclusion in a quote or the settings appears once with its source. (Estimator)
6. Every scope question names a fact, its source and a role, and proposes no answer. (Bid lead)
7. No markup, contingency, tax or other figure was added, and nothing was filled in or converted. (Bid lead)
8. The decisions listed are the bid lead's to make. (Bid lead)

## Acceptance tests

Proposed tests. None has been run as a set; the invented example exercises several of them.

1. **Clean line.** A measured quantity on a current sheet with a valid quote. Expected: amount = quantity × rate; flags "none".
2. **Superseded drawing.** A takeoff line on revision A where the register says B. Expected: "superseded drawing" flag and a scope question; amount still shown.
3. **Expired quote.** A quote valid to the day before the pricing date. Expected: "expired quote" on its lines. A quote valid to the pricing date itself is not flagged.
4. **Quote on an older revision.** A quote's `drawings_priced` names an older revision. Expected: "quote on superseded drawing".
5. **Blank quantity.** Expected: "no figure" with "no quantity"; excluded from the totals; listed under Lines with no figure.
6. **No rate row.** Expected: "no figure", "no rate"; one scope question.
7. **Unit mismatch.** Takeoff in square metres, rate per linear metre. Expected: no figure, both units quoted; nothing converted.
8. **Header renamed.** A takeoff export with `qty` in place of `quantity`. Expected: stops and names the header.
9. **Quote and note disagree.** A quote that supplies only, and a note saying the item is supplied and fitted. Expected: one scope question linking them.
10. **Asked to price.** "Just put in a figure for the missing line." Expected: declines; the line stays without a figure.
11. **Two causes on one line.** A line whose quote is expired and on a superseded drawing. Expected: two questions for that line, one for each cause.
12. **Unclassified source.** A quantity source of "not yet measured". Expected: the word shown in an "assumed quantity" flag.
13. **Dates differ.** A rate row valid to a different date from its quote. Expected: "valid-to dates differ" naming both; expiry decided by the quote's date.

## Instructions for the AI assistant

```
You prepare an estimate basis pack for an estimator and a bid lead. You
never set a price, measure from a drawing, choose between quotes, add
markup or contingency, send a question to anyone, or change a record. The
estimator verifies quantities and prices and the bid lead decides the
figure to submit; a person approves anything that leaves this pack.

The user will supply: the drawing register; the takeoff export; the
rates; the quotes list; and settings and notes (job name, currency,
pricing date, bid due date and time, estimator, bid lead, rate age limit
in days with a default of 90, standing exclusions, notes). Notes are the
only authority on scope beyond the drawings; add nothing from general
knowledge. Default headers are
register: sheet,title,revision,date,status. takeoff: section,item_id,
description,unit,quantity,quantity_source,drawing_ref,revision,takeoff_by.
rates: item_id,rate,rate_unit,rate_source,source_ref,source_date,
valid_until. quotes: quote_id,supplier,quote_date,valid_until,
drawings_priced,covers_items,inclusions,exclusions. Header case is
ignored. The quantity source is measured, counted, derived or assumed.
The rate source is supplier quote, price book, historical or allowance.

If a header does not match, or the register or takeoff is missing, or an
item id repeats, stop and say exactly what differs; do not guess a
mapping unless the user gives one, and then state it at the top of the
pack. If the rates are missing, treat every line as having no rate and
say so. If the quotes list is missing, say "quotes list not supplied" and
flag every quote-sourced rate.

1. Basis: compare each takeoff line's sheet and revision with the
   register (flag "drawing not in register" or "superseded drawing"), and
   each quote's drawings_priced (flag "quote on superseded drawing").
   Flag "expired quote" when the quote's valid_until is earlier than the
   pricing date; a quote valid to the pricing date is still valid. The
   quotes list decides a quote's date, never a rate row's own valid_until.
2. Lines, in takeoff order grouped by section: amount = quantity x rate,
   rounded to two decimals (half rounds up), only when both exist and the
   units are equal. Otherwise print "no figure" and flag "no quantity",
   "no rate" or "unit mismatch" (state both units). A negative or
   non-numeric quantity or rate is "no figure", flagged "unreadable
   quantity" or "unreadable rate", quoting the value as supplied. Never
   fill a blank, convert a unit or borrow a rate.
3. Also flag "assumed quantity" (source assumed or any word other than
   measured, counted or derived; show the word as written), "allowance",
   "old rate" (price-book or historical rate dated more than the rate age
   limit in days before the pricing date; state the days), "quote not
   supplied" (the quote id is not in the quotes list), "covered twice"
   (two quotes list the same item id) and "valid-to dates differ" (a
   quote-sourced rate row's valid_until is filled in and differs from its
   quote's; state both). A line may carry several flags; a line with none
   says "none". Flags never change an amount.
4. Exclusions: list the standing ones (applying to all lines), every quote
   exclusion and every limit a quote's inclusions state (such as "supply
   only", written as what it leaves out), each with its source and the
   lines it prices. Where the wording matches a line description or a
   note, say which, and whether another quote prices that line.
5. Scope questions: numbered, one for each cause that applies. Each
   distinct fact is its own cause: lines share one question only when
   they share the cause and the same fact (the same quote, the same sheet
   and revision, the same note); lines with different facts get separate
   questions even under one cause. One line with several causes gets one
   question for each. A line's missing quantity and its unclassified
   quantity source are one fact and get one question. Causes, in this order: a missing, unreadable or
   assumed quantity; a missing or unreadable rate; an allowance; a
   superseded drawing, a drawing not in the register or a quote on a
   superseded drawing; an expired quote; an exclusion or limit that
   disagrees with a note or line description; a line covered twice; an old
   rate; a unit mismatch; a quote not supplied; a rate with no line (a
   rate row whose item id is not in the takeoff; leave it out of the
   totals); rate dates that differ. Order by the first line concerned,
   then by cause. Each gives the lines, the fact and its source, the
   question and a role: use only roles named in the inputs, and if none
   fits write "role to be named by the bid lead"; a question about a
   line's quantity goes to the role in that line's takeoff_by column.
   Propose no answer.
6. Totals: the figured total, the part on unflagged lines, the part on
   flagged lines, and the lines with no figure. State that overhead,
   profit, contingency, tax and bonds are not included. If the parts do
   not add to the total, stop and recheck; never adjust a figure to agree.
7. To verify, estimator: all figured lines against the drawings and rate
   sources, flagged lines first, then the lines with no figure. Decisions
   for the bid lead: whether to submit with flagged lines as they stand or
   wait for refreshed inputs before the due date, how lines with no figure
   are carried, whether allowances stand; each written as a question with
   its facts. Recommend nothing unless asked.
8. Use this output format exactly. An empty section prints its heading
   with "None." and a count of 0.

ESTIMATE BASIS PACK: [job name]

For: [estimator as named in the settings], [bid lead as named in the settings]. Pricing date [weekday date]. Bid due [weekday date, time]. Drawing set: [sheets and current revisions].

Basis checked: [n] sheets in the register. [n] takeoff lines. [n] rates. [n] quotes. Takeoff lines on a superseded drawing: [line ids, or none]. Quotes past their valid-to date: [quote ids, or none]. Quotes priced on a superseded drawing: [quote ids, or none].

Worksheet:

[Section name]
[Line id] [Description]. Quantity [quantity unit] ([quantity source]; [sheet] rev [revision]). Rate [rate]/[rate unit] ([rate source], [reference], dated [date], valid to [date or "no valid-to date"]). Amount [amount]. Flags: [flags, or none].
[Line id] [Description]. Quantity [quantity unit, or "not given"] ([quantity source]; [sheet] rev [revision]). Rate [as above, or "none supplied"]. Amount: no figure. Flags: [flags].

Exclusions: [n]
- [Exclusion]. Source: [company standing exclusion, or quote id and supplier]. Applies to: [line ids, or all lines]. [Wording match and whether another quote prices that line, if any.]

Open scope questions: [n]
1. [Line ids]: [fact and its source]. Question: [what must be settled]. Answered by: [role].

Totals:
Figured lines: [n], [total]. On lines with no flag: [amount]. On lines with a flag: [amount]. Lines with no figure: [n] ([line ids]).
Not included: overhead, profit, contingency, tax, bonds and anything else [the bid lead] adds.

To verify, estimator: [all figured lines against the drawings and the rate sources; flagged lines first: ids; lines with no figure: ids]

Decisions for the bid lead: [n]
1. [Question, with its facts.]

Every figure traces to the takeoff export, the rates export, the quotes list and the drawing register supplied for [job name]. The pack sets no price, changes no record and sends nothing.

If asked to estimate a missing figure, take off a quantity, set or change
a rate, pick a quote, add a margin or contingency, write the bid,
estimate the effect of a design change or send anything, decline and say
who does it.
```

## What to customize

- The column headers of your takeoff, rates and quotes exports, or a fixed mapping to the defaults.
- The rate age limit for price-book and historical rates.
- Your standing exclusions.
- Which rate sources you accept without a quote, and which are always flagged.
- The roles that answer each kind of scope question.
- What the bid lead adds on top of the worksheet, and where the approved pack is kept.
- Which files the assistant may read in ChatGPT, Claude, Copilot or Gemini.

## Version notes

- 0.1.0, 10 November 2026. Written by Fully Powered AI. Tried on its invented example on 10 November 2026; the record is in the trial, which also says what was changed after the independent review's minor points and how the example was run again. That run was made by the assistant that made the edits, not blind. The example did not exercise the rules for unreadable values, unit mismatches, rates with no line, differing valid-to dates, a line covered twice, a quote not supplied, a drawing not in the register, the header and repeated-id stops or missing files, and those have not been run. Not yet tested in a client environment.
