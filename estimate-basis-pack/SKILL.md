---
name: "estimate-basis-pack"
description: "Prepare the worksheet an estimator and a bid lead price from: every figure built only from a supplied quantity and a supplied rate, with the quantity's source, the rate's source and date, the drawing revision and any reason for doubt written beside it. The worksheet also lists the exclusions and turns every gap into a numbered scope question for a named role. The assistant prepares and checks. It sets no price, performs no takeoff, makes no engineering judgment, chooses no quote and sends nothing. The estimator verifies quantities and prices; the bid lead decides the figure to submit."
license: "MIT"
metadata:
  version: "0.1.0"
  publisher: "Fully Powered AI"
  template: "Estimate basis pack"
---

# Estimate basis pack

This is the technical file for a Fully Powered workflow template. It carries the instructions an AI product follows. The complete template, with roles, inputs, exceptions, the reviewer checklist, acceptance tests and what to customize, is in [TEMPLATE.md](TEMPLATE.md). A worked example with invented data is in [EXAMPLE.md](EXAMPLE.md).

## Instructions

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

## Before relying on it

Decide every item under "What to customize" in TEMPLATE.md and set the limits the instructions in this file leave open, written in square brackets such as [N], to your own. Then run the acceptance tests in TEMPLATE.md on past work. A person starts this work, supplies the inputs and decides what happens with the result.
