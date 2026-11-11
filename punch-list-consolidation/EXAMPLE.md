# Punch list consolidation: an invented example

*Illustrative example with invented data.* The project, the trades, the items, the dates and every figure below are invented, and the trades are named Trade A to Trade F. The project is a small two-storey building called the Lakeside Annex here. The site manager runs the consolidation on Tuesday 17 November 2026, after that day's closeout walk. People are referred to by role.

The inputs come first, in full, so the template can be run on them. The consolidated list follows.

## The inputs

### 1. Settings (typed by the site manager)

```
Project: the Lakeside Annex
Today: Tuesday 17 November 2026
Walk date: Tuesday 17 November 2026
Target closeout: Friday 11 December 2026
Decides: the site manager
```

The days allowed before a check and the next walk date were not given, so the default of 7 days is used and the next walk is not supplied. Days are counted as calendar days.

### 2. Prior punch list

```
item_no,location,trade,description,date_added,recorded_status,contractor_note,assigned_to,due_date,verified_by,verified_date
P-01,Level 1 Corridor,Trade A,Touch-up paint scuffs on north wall,2026-11-03,open,,Trade A,2026-11-13,,
P-02,Level 1 Room 1.04,Trade B,Replace cracked floor tile at doorway,2026-11-03,contractor reports complete,Replaced 12 Nov,Trade B,2026-11-13,,
P-03,Level 1 Room 1.04,Trade C,Door closer does not latch,2026-11-03,verified closed,,Trade C,2026-11-10,Quality lead,2026-11-12
P-04,Level 2 Room 2.01,Trade D,Missing cover plate on data outlet,2026-11-03,open,,Trade D,2026-11-20,,
P-05,Level 2 Room 2.02,Trade A,Seal gap at window sill,2026-11-03,open,,Trade A,2026-11-10,,
P-06,Roof,Trade E,Clear debris from roof drain,2026-11-03,open,,Trade E,,,
```

### 3. Walk notes

```
note_no,walk_date,location,trade,observation,photo_ref,refers_to
W-01,2026-11-17,Level 1 Corridor,Trade A,Touch-up paint scuffs on north wall,IMG-101,
W-02,2026-11-17,Level 1 Room 1.04,Trade B,Tile at doorway has cracked again along the grout line,IMG-102,P-02
W-03,2026-11-17,Level 2 Room 2.01,Trade D,Missing cover plate on data outlet,IMG-103,
W-04,2026-11-17,Level 2 Room 2.01,Trade F,Ceiling tile stained above desk position 3,IMG-104,
W-05,2026-11-17,Level 2 Room 2.01,Trade F,Stained ceiling tile above desk 3,,
W-06,2026-11-17,Level 1 Room 1.04,Trade C,Door closer does not latch,IMG-105,P-03
W-07,2026-11-17,Level 2 Stair,,Handrail loose at lower bracket,IMG-106,
W-08,2026-11-17,Level 2 Room 2.02,Trade A,Seal gap at window sill,,
```

### 4. Contractor updates

```
update_no,item_no,location,trade,update_text,update_date,reports_complete,promised_date,photo_ref
U-01,P-01,Level 1 Corridor,Trade A,Touch-up scheduled,2026-11-16,no,2026-11-20,
U-02,P-04,Level 2 Room 2.01,Trade D,Cover plate on order,2026-11-16,no,2026-11-25,
U-03,P-06,Roof,Trade E,Drain cleared and debris removed,2026-11-16,yes,,IMG-107
U-04,,Level 2 Room 2.02,Trade A,Sealant to be applied Thursday,2026-11-16,no,2026-11-19,
```

## The output

**PUNCH LIST CONSOLIDATION: the Lakeside Annex, walk of Tuesday 17 November 2026**

For: the site manager. Prepared Tuesday 17 November 2026 from: prior punch list (6 rows), walk notes (8 rows), contractor updates (4 rows), settings.  
Column check: all headers matched.  
Settings: walk date Tuesday 17 November 2026, follow-up 7 days, next walk not supplied, target closeout Friday 11 December 2026, counted in calendar days. Defaults used: follow-up days.  
Summary: 9 items. Open 7 (overdue 3). Contractor reports complete, awaiting verification 1. Verified closed 1. Raised again at the walk 2. Walk notes 8: merged into existing items 5, new items 3. Contractor updates attached 4. Possible duplicates not merged 1 pair. Items with no photograph 2. Trade not stated 1. Proposed follow-up dates 8 (trade's own date 3, existing due date 0, next walk 0, default 4, verification 1); after target closeout 0.

**Data checks**

- U-04 has no item number. It was attached to P-05, the only item with the same location and trade (Level 2 Room 2.02, Trade A).
- W-07 has no trade. Its item is listed under "Trade not stated".
- P-06 has no due date. None was invented.
- No verified closed row is missing its verifier or date.
- No walk note or update uses the words unsafe, hazard or danger.
- No location or trade is written several ways.

**Punch list**

**Level 1 Corridor**

*Trade A*

- **P-01** Touch-up paint scuffs on north wall. OPEN. Overdue by 4 days (due Friday 13 November 2026). Merged: P-01, W-01 (same text). Update U-01, Monday 16 November 2026: "Touch-up scheduled", promised Friday 20 November 2026. Evidence: IMG-101 (walk, Tuesday 17 November 2026). Proposed follow-up: Friday 20 November 2026 (trade's date), 7 days later than the existing due date.

**Level 1 Room 1.04**

*Trade B*

- **P-02** Replace cracked floor tile at doorway. OPEN. Overdue by 4 days (due Friday 13 November 2026). Raised again at the walk, Tuesday 17 November 2026: "Tile at doorway has cracked again along the grout line". Merged: P-02, W-02 (the walk note names P-02). Earlier contractor note: "Replaced 12 Nov". Evidence: IMG-102 (walk, Tuesday 17 November 2026). Proposed follow-up: Tuesday 24 November 2026 (default, walk date plus 7 days), 11 days later than the existing due date.

*Trade C*

- **P-03** Door closer does not latch. VERIFIED CLOSED: Quality lead, Thursday 12 November 2026. Raised again at the walk, Tuesday 17 November 2026, with the same wording. Merged: P-03, W-06 (the walk note names P-03). Evidence: IMG-105 (walk, Tuesday 17 November 2026). Proposed follow-up: none until the site manager decides.

**Level 2 Room 2.01**

*Trade D*

- **P-04** Missing cover plate on data outlet. OPEN. Due Friday 20 November 2026. Merged: P-04, W-03 (same text). Update U-02, Monday 16 November 2026: "Cover plate on order", promised Wednesday 25 November 2026. Evidence: IMG-103 (walk, Tuesday 17 November 2026). Proposed follow-up: Wednesday 25 November 2026 (trade's date), 5 days later than the existing due date.

*Trade F*

- **NEW-1** Ceiling tile stained above desk position 3. OPEN. Merged: W-04. Evidence: IMG-104 (walk, Tuesday 17 November 2026). Possible duplicate of NEW-2. Proposed follow-up: Tuesday 24 November 2026 (default, walk date plus 7 days).
- **NEW-2** Stained ceiling tile above desk 3. OPEN. Merged: W-05. No photograph supplied. Possible duplicate of NEW-1. Proposed follow-up: Tuesday 24 November 2026 (default, walk date plus 7 days).

**Level 2 Room 2.02**

*Trade A*

- **P-05** Seal gap at window sill. OPEN. Overdue by 7 days (due Tuesday 10 November 2026). Merged: P-05, W-08 (same text). Update U-04, Monday 16 November 2026: "Sealant to be applied Thursday", promised Thursday 19 November 2026. No photograph supplied. Proposed follow-up: Thursday 19 November 2026 (trade's date), 9 days later than the existing due date.

**Level 2 Stair**

*Trade not stated*

- **NEW-3** Handrail loose at lower bracket. OPEN. Merged: W-07. Evidence: IMG-106 (walk, Tuesday 17 November 2026). Proposed follow-up: Tuesday 24 November 2026 (default, walk date plus 7 days).

**Roof**

*Trade E*

- **P-06** Clear debris from roof drain. CONTRACTOR REPORTS COMPLETE, not verified. Update U-03, Monday 16 November 2026: "Drain cleared and debris removed", reports complete. Evidence: IMG-107 (contractor update, Monday 16 November 2026). No due date recorded. Proposed follow-up: Tuesday 24 November 2026 (verification, default, walk date plus 7 days).

**Possible duplicates, not merged: 1 pair**

- NEW-1 and NEW-2, Level 2 Room 2.01, Trade F. Same location and trade, different wording: "Ceiling tile stained above desk position 3" and "Stained ceiling tile above desk 3".

**Raised again at the walk: 2**

- P-02, reported complete with the note "Replaced 12 Nov", seen again on Tuesday 17 November 2026. Now shown as OPEN.
- P-03, verified closed by the Quality lead on Thursday 12 November 2026, seen again on Tuesday 17 November 2026. Still shown as VERIFIED CLOSED until the site manager decides.

**Reported complete, awaiting verification: 1**

- P-06 Clear debris from roof drain (Trade E): reported Monday 16 November 2026, with IMG-107. Proposed check Tuesday 24 November 2026.

**Overdue open items: 3**

- P-05 Seal gap at window sill: 7 days (due Tuesday 10 November 2026).
- P-01 Touch-up paint scuffs on north wall: 4 days (due Friday 13 November 2026).
- P-02 Replace cracked floor tile at doorway: 4 days (due Friday 13 November 2026).

**Items with no photograph: 2**

- P-05 Seal gap at window sill (Level 2 Room 2.02, Trade A).
- NEW-2 Stained ceiling tile above desk 3 (Level 2 Room 2.01, Trade F).

**Questions for the site manager**

1. P-01 Touch-up paint scuffs on north wall (Trade A). Open and 4 days past its due date of Friday 13 November 2026. Trade A's update of Monday 16 November 2026 says "Touch-up scheduled", promised Friday 20 November 2026, 7 days after the due date. What date do you want to set?
2. P-02 Replace cracked floor tile at doorway (Trade B). Trade B's earlier note said "Replaced 12 Nov"; the walk on Tuesday 17 November 2026 found the tile cracked along the grout line (IMG-102). It is 4 days past its due date of Friday 13 November 2026 and Trade B has promised no date. The proposed check of Tuesday 24 November 2026 is 11 days after the due date. What do you want done?
3. P-03 Door closer does not latch (Trade C). The Quality lead verified it closed on Thursday 12 November 2026. The walk on Tuesday 17 November 2026 recorded the same wording, with IMG-105. It still shows as VERIFIED CLOSED. What do you want done?
4. P-04 Missing cover plate on data outlet (Trade D). Due Friday 20 November 2026. Trade D promises Wednesday 25 November 2026, 5 days later, and the target closeout is Friday 11 December 2026. What date do you want to set?
5. P-05 Seal gap at window sill (Trade A). Open, 7 days past its due date of Tuesday 10 November 2026, with no photograph. Trade A's update, which had no item number and was matched by location and trade, says "Sealant to be applied Thursday", promised Thursday 19 November 2026, 9 days after the due date. What do you want done?
6. P-06 Clear debris from roof drain (Trade E). Trade E reported the work complete on Monday 16 November 2026 with IMG-107; nobody has verified it. What do you want done?
7. NEW-1 and NEW-2 (Level 2 Room 2.01, Trade F). Same location and trade, different wording: "Ceiling tile stained above desk position 3" (IMG-104) and "Stained ceiling tile above desk 3" (no photograph). What do you want done with the pair?
8. NEW-3 Handrail loose at lower bracket (Level 2 Stair). The walk note states no trade. What do you want done?

Completion is accepted only by the authorized inspector or owner representative. A trade's note that work is complete is not verified closure, and assigning the work is the site manager's decision.

Draft for the site manager's decisions. No trade, inspector or owner representative has been contacted, and no punch list, status or due date has been changed.
