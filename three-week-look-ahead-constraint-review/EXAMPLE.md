# Three-week look-ahead constraint review: an invented example

*Illustrative example with invented data.* The project, the trades, the suppliers, the activity codes and every date below are invented. The project is an invented interior fit-out of a three-storey office building called Marlow Yard Block C. Trades and suppliers are named by letter (Electrical A, Supplier B). People are named by role. First come the inputs the project engineer supplied, in full, then the brief the workflow template returned.

## The inputs

### 1. Settings

```
Project: Marlow Yard Block C interior fit-out
Superintendent: Superintendent
Prepared by: Project engineer
Check date: Thursday 12 November 2026
Meeting: Friday 13 November 2026
Window: 3 weeks
Working days: Monday to Friday
Closed days in the window: Thursday 26 November 2026, Friday 27 November 2026
```

### 2. Schedule extract

```
activity_id,activity,trade,location,start,finish,predecessors,status
A100,Level 2 east layout and marking,Layout A,Level 2 east,2026-11-04,2026-11-06,-,complete
A101,Level 2 east ceiling duct rough-in,Mechanical A,Level 2 east,2026-11-09,2026-11-17,A100,in progress
A102,Level 2 east electrical rough-in,Electrical A,Level 2 east,2026-11-12,2026-11-20,A100,not started
A103,Level 2 east drywall hang,Drywall A,Level 2 east,2026-11-23,2026-12-02,A101; A102,not started
A104,Level 3 west framing,Framing A,Level 3 west,2026-11-02,2026-11-11,-,in progress
A105,Level 3 west electrical rough-in,Electrical A,Level 3 west,2026-11-12,2026-11-24,A104,not started
A106,Ground floor storefront glazing install,Glazing A,Ground floor front,2026-11-16,2026-11-20,-,not started
A107,Roof unit set,Mechanical A,Roof,2026-11-30,2026-12-01,-,not started
A108,Level 2 east ceiling grid,Ceiling A,Level 2 east,2026-11-30,2026-12-02,A103,not started
A109,Level 3 west duct rough-in,Mechanical A,Level 3 west,2026-11-17,2026-11-25,A104,not started
A111,Level 2 east flooring,Flooring A,Level 2 east,2026-12-07,2026-12-11,A108,not started
```

### 3. Trade updates

```
update_id,activity_id,trade,reported_on,reported_start,reported_finish,crew,note
U01,A101,Mechanical A,2026-11-10,2026-11-09,2026-11-19,4,Crew of 4; no second shift
U02,A102,Electrical A,2026-11-11,2026-11-12,2026-11-20,3,
U03,A104,Framing A,2026-11-11,2026-11-02,2026-11-13,5,Two walls on hold for RFI-014
U04,A106,Glazing A,2026-11-02,2026-11-16,2026-11-20,4,
U05,A103,Drywall A,2026-11-10,2026-11-23,2026-12-02,6,
U06,A109,Mechanical A,2026-11-10,2026-11-17,2026-11-25,3,
U07,A107,Mechanical A,2026-11-09,2026-11-30,2026-12-01,2,Crane booked for 30 November
U08,A104,Framing A,2026-11-04,2026-11-02,2026-11-11,5,
U09,A120,Plumbing A,2026-11-10,2026-11-18,2026-11-20,2,
```

### 4. Deliveries

```
delivery_id,item,activity_id,supplier,needed_on,promised_on,status
D01,Storefront glazing units,A106,Supplier A,2026-11-16,2026-11-24,confirmed
D02,Rooftop unit,A107,Supplier B,2026-11-30,2026-11-27,confirmed
D03,Level 3 duct sections,A109,Supplier C,2026-11-17,2026-11-16,shipped
D04,Ceiling grid and tile,A108,Supplier D,2026-11-30,,ordered
D05,Drywall boards,A103,Supplier E,2026-11-23,2026-11-10,delivered
D06,Fire-rated door frames,,Supplier F,2026-11-20,,not ordered
D07,Flooring adhesive,A111,Supplier G,2026-12-07,2026-12-04,shipped
```

### 5. RFI log

```
rfi_id,subject,activity_id,issued_on,needed_by,status,answered_on
RFI-011,Door hardware group,A103,2026-10-26,2026-11-06,answered,2026-11-03
RFI-014,Wall type at grid C,A104,2026-10-28,2026-11-06,open,
RFI-017,Duct conflict at beam,A109,2026-11-05,2026-11-16,open,
RFI-018,Corridor ceiling height,A108,2026-11-09,2026-11-25,open,
RFI-019,Roof curb dimension,A107,2026-11-10,2026-12-14,open,
```

### 6. Approvals and submittals log

```
item_id,item,kind,activity_id,submitted_on,needed_by,status
S01,Storefront glazing shop drawings,submittal,A106,2026-10-20,2026-11-06,revise and resubmit
S02,Ceiling grid product data,submittal,A108,2026-11-02,2026-11-18,submitted
S03,Level 3 west electrical permit amendment,permit,A105,,2026-11-11,not submitted
S04,Corridor ceiling finish,owner decision,A108,2026-11-03,2026-11-20,submitted
S05,Drywall board product data,submittal,A103,2026-10-28,2026-11-02,approved as noted
```

### 7. Access claims

```
claim_id,area,trade,activity_id,from,to,exclusive
X1,Level 3 west,Electrical A,A105,2026-11-12,2026-11-24,yes
X2,Level 3 west,Mechanical A,A109,2026-11-17,2026-11-25,yes
X3,Level 2 east,Mechanical A,A101,2026-11-09,2026-11-17,no
X4,Level 2 east,Electrical A,A102,2026-11-12,2026-11-20,no
X5,Level 2 east,Drywall A,A103,2026-11-23,2026-12-02,yes
X6,Level 2 east,Ceiling A,A108,2026-11-30,2026-12-02,yes
```

## The output

**THREE-WEEK LOOK-AHEAD CONSTRAINT REVIEW: Marlow Yard Block C interior fit-out**

For: Superintendent. Prepared by: Project engineer. Check date: Thursday 12 November 2026. Meeting: Friday 13 November 2026.
Window: Thursday 12 November 2026 to Wednesday 2 December 2026 (3 weeks). Working days: Monday to Friday. Closed days in the window: Thursday 26 November 2026, Friday 27 November 2026.
Supplied: schedule (11 activities); trade updates (9 rows, 1 superseded); deliveries (7 rows); RFIs (5 rows); approvals (5 rows); access claims (6 rows).
Not supplied: none. Checks not made because of it: none.
Activities in the window: 9. Left out: 2. Activities with a constraint: 9.
Items to chase: approvals 4, deliveries 3, RFIs 4.

**ALREADY UNDER WAY OR PAST ITS FINISH**

A104 Level 3 west framing. Framing A, Level 3 west. Scheduled Monday 2 November to Wednesday 11 November. Status: in progress. Waits on: nothing.

- Trade update: Wednesday 11 November, Monday 2 November to Friday 13 November, crew 5, note: "Two walls on hold for RFI-014".
- Constraints:
  - Dates: scheduled finish Wednesday 11 November has passed and the activity is not complete (1 working day past). Framing A reports finish Friday 13 November, 2 working days later than scheduled.
  - Overlap: O2, with A105.
  - RFI: RFI-014, open, needed by Friday 6 November, overdue by 4 working days.

A101 Level 2 east ceiling duct rough-in. Mechanical A, Level 2 east. Scheduled Monday 9 November to Tuesday 17 November. Status: in progress. Waits on: A100.

- Trade update: Tuesday 10 November, Monday 9 November to Thursday 19 November, crew 4, note: "Crew of 4; no second shift".
- Constraints:
  - Dates: Mechanical A reports finish Thursday 19 November, 2 working days later than scheduled.
  - Overlap: O1, with A102.

**WEEK 1: Thursday 12 November to Wednesday 18 November**

A102 Level 2 east electrical rough-in. Electrical A, Level 2 east. Scheduled Thursday 12 November to Friday 20 November. Status: not started. Waits on: A100.

- Trade update: Wednesday 11 November, Thursday 12 November to Friday 20 November, crew 3.
- Constraints:
  - Overlap: O1, with A101.

A105 Level 3 west electrical rough-in. Electrical A, Level 3 west. Scheduled Thursday 12 November to Tuesday 24 November. Status: not started. Waits on: A104.

- Trade update: none on file.
- Constraints:
  - Waits on unfinished work: A104 is in progress. Both tests apply: its scheduled finish, Wednesday 11 November, is before the check date, and its reported finish, Friday 13 November, is after A105's scheduled start, Thursday 12 November.
  - Trade update: no trade update on file.
  - Overlap: O2, with A104; O3, with A109.
  - Approval: S03, not submitted, needed by Wednesday 11 November, overdue by 1 working day.

A106 Ground floor storefront glazing install. Glazing A, Ground floor front. Scheduled Monday 16 November to Friday 20 November. Status: not started. Waits on: nothing.

- Trade update: stale: Monday 2 November, Monday 16 November to Friday 20 November, crew 4.
- Constraints:
  - Trade update: stale update, 10 days before the check date.
  - Approval: S01, revise and resubmit, back with the submitter, needed by Friday 6 November, overdue by 4 working days.
  - Delivery: D01, promised Tuesday 24 November, 6 working days after the date needed.

A109 Level 3 west duct rough-in. Mechanical A, Level 3 west. Scheduled Tuesday 17 November to Wednesday 25 November. Status: not started. Waits on: A104.

- Trade update: Tuesday 10 November, Tuesday 17 November to Wednesday 25 November, crew 3.
- Constraints:
  - Waits on unfinished work: A104 is in progress and its scheduled finish, Wednesday 11 November, is before the check date; its reported finish, Friday 13 November, is before A109's scheduled start, Tuesday 17 November.
  - Overlap: O3, with A105.
  - Delivery: D03, shipped, promised Monday 16 November for Tuesday 17 November, on time as promised (not counted).
  - RFI: RFI-017, open, needed by Monday 16 November, due in the window.

**WEEK 2: Thursday 19 November to Wednesday 25 November**

A103 Level 2 east drywall hang. Drywall A, Level 2 east. Scheduled Monday 23 November to Wednesday 2 December. Status: not started. Waits on: A101; A102.

- Trade update: Tuesday 10 November, Monday 23 November to Wednesday 2 December, crew 6.
- Constraints:
  - Overlap: O4, with A108.

**WEEK 3: Thursday 26 November to Wednesday 2 December**

A107 Roof unit set. Mechanical A, Roof. Scheduled Monday 30 November to Tuesday 1 December. Status: not started. Waits on: nothing.

- Trade update: Monday 9 November, Monday 30 November to Tuesday 1 December, crew 2, note: "Crane booked for 30 November".
- Constraints:
  - Delivery: D02, promised Friday 27 November, a closed day; needed Monday 30 November.
  - RFI: RFI-019, open, needed by Monday 14 December, which is after the activity starts on Monday 30 November.

A108 Level 2 east ceiling grid. Ceiling A, Level 2 east. Scheduled Monday 30 November to Wednesday 2 December. Status: not started. Waits on: A103.

- Trade update: none on file.
- Constraints:
  - Waits on unfinished work: A103 is not started and its scheduled finish, Wednesday 2 December, is after A108's scheduled start, Monday 30 November.
  - Trade update: no trade update on file.
  - Overlap: O4, with A103.
  - Approval: S02, submitted, with the reviewer 8 working days, needed by Wednesday 18 November; S04, submitted, with the reviewer 7 working days, needed by Friday 20 November.
  - Delivery: D04, no promised date; status ordered, so the supplier has not confirmed.
  - RFI: RFI-018, open, needed by Wednesday 25 November, due in the window.

**TRADE OVERLAPS**

- **O1** A101 (Mechanical A) and A102 (Electrical A), Level 2 east. Scheduled overlap: Thursday 12 November to Tuesday 17 November, 4 working days. On reported dates: Thursday 12 November to Thursday 19 November, 6 working days. Access: shared access (X3, X4).
- **O2** A104 (Framing A) and A105 (Electrical A), Level 3 west. Scheduled overlap: none, 0 working days. On reported dates: Thursday 12 November to Friday 13 November, 2 working days. Access: no access claim on file for A104.
- **O3** A105 (Electrical A) and A109 (Mechanical A), Level 3 west. Scheduled overlap: Tuesday 17 November to Tuesday 24 November, 6 working days. Access: access conflict (X1, exclusive, Thursday 12 November to Tuesday 24 November; X2, exclusive, Tuesday 17 November to Wednesday 25 November).
- **O4** A103 (Drywall A) and A108 (Ceiling A), Level 2 east. Scheduled overlap: Monday 30 November to Wednesday 2 December, 3 working days. Access: access conflict (X5, exclusive, Monday 23 November to Wednesday 2 December; X6, exclusive, Monday 30 November to Wednesday 2 December).

**OPEN APPROVALS AND SUBMITTALS**

- **S01** Storefront glazing shop drawings (submittal), for A106. Status: revise and resubmit. Needed by Friday 6 November. Back with the submitter; overdue by 4 working days. Assigned to: ______
- **S03** Level 3 west electrical permit amendment (permit), for A105. Status: not submitted. Needed by Wednesday 11 November. Nothing has gone to the reviewer; overdue by 1 working day. Assigned to: ______
- **S02** Ceiling grid product data (submittal), for A108. Status: submitted Monday 2 November. Needed by Wednesday 18 November. With the reviewer 8 working days. Assigned to: ______
- **S04** Corridor ceiling finish (owner decision), for A108. Status: submitted Tuesday 3 November. Needed by Friday 20 November. With the reviewer 7 working days. Assigned to: ______

Clear and not listed: none.

**DELIVERIES**

- **D01** Storefront glazing units, for A106, Supplier A. Needed Monday 16 November. Promised Tuesday 24 November. Status: confirmed. Promised after the date needed, 6 working days late. Assigned to: ______
- **D03** Level 3 duct sections, for A109, Supplier C. Needed Tuesday 17 November. Promised Monday 16 November. Status: shipped. On time as promised, not counted.
- **D02** Rooftop unit, for A107, Supplier B. Needed Monday 30 November. Promised Friday 27 November. Status: confirmed. Promised for a closed day. Assigned to: ______
- **D04** Ceiling grid and tile, for A108, Supplier D. Needed Monday 30 November. Promised: none. Status: ordered. No promised date; the supplier has not confirmed. Assigned to: ______

Clear and not listed: D05.

**RFIS**

- **RFI-014** Wall type at grid C, for A104. Issued Wednesday 28 October. Needed by Friday 6 November. Overdue by 4 working days. Assigned to: ______
- **RFI-017** Duct conflict at beam, for A109. Issued Thursday 5 November. Needed by Monday 16 November. Due in the window. Assigned to: ______
- **RFI-018** Corridor ceiling height, for A108. Issued Monday 9 November. Needed by Wednesday 25 November. Due in the window. Assigned to: ______
- **RFI-019** Roof curb dimension, for A107. Issued Tuesday 10 November. Needed by Monday 14 December. Needed after the activity starts. Assigned to: ______

Clear and not listed: RFI-011.

**QUESTIONS FOR THE SUPERINTENDENT**

1. **A104, Level 3 west framing.** Its scheduled finish, Wednesday 11 November, has passed and it is in progress. Framing A reports finish Friday 13 November, 2 working days later than scheduled, with two walls on hold for RFI-014, which is 4 working days overdue. A105 and A109 wait on it. Do you accept Friday 13 November for sequencing, and which trade lead confirms Framing A's capacity?
2. **A101, Level 2 east ceiling duct rough-in.** Mechanical A reports finish Thursday 19 November, 2 working days later than the scheduled Tuesday 17 November, with a crew of 4 and no second shift. A103 waits on it and is scheduled to start Monday 23 November. Does A103 still start on Monday 23 November, and which trade lead confirms Mechanical A's finish?
3. **A105, Level 3 west electrical rough-in.** It is scheduled to start today, Thursday 12 November. It waits on A104, whose scheduled finish has passed and whose reported finish, Friday 13 November, is after A105's start. There is no trade update on file, so its duration is not confirmed by the trade, and permit amendment S03 has not been submitted. Nothing waits on it. Does A105 start on Thursday 12 November, and which trade lead confirms Electrical A's start and duration?
4. **A106, Ground floor storefront glazing install.** The latest update from Glazing A is Monday 2 November, 10 days before the check date, and shows the scheduled dates. The glazing units are promised Tuesday 24 November, 6 working days after the date needed (D01), and the shop drawings (S01) are back with the submitter, 4 working days overdue. Nothing waits on it. Does the start on Monday 16 November hold, and which trade lead gives a current update?
5. **A109, Level 3 west duct rough-in.** It waits on A104, whose scheduled finish has passed; the reported finish, Friday 13 November, is before A109's scheduled start on Tuesday 17 November. RFI-017 is open and needed by Monday 16 November, the day before the start. The duct sections are shipped and promised for Monday 16 November (D03). Nothing waits on it. Does A109 start on Tuesday 17 November, and which trade lead confirms Mechanical A's capacity?
6. **A108, Level 2 east ceiling grid.** The schedule starts it on Monday 30 November, but A103, which it waits on, is scheduled to finish on Wednesday 2 December. There is no trade update on file. The ceiling grid delivery (D04) has no promised date, and S02, S04 and RFI-018 are open. A111, outside the window, waits on it. Which is right, A108's start or A103's finish, and which trade lead confirms Ceiling A's dates?
7. **O1, Level 2 east: A101 and A102.** The two trades share Level 2 east for 4 working days as scheduled and 6 as reported, from Thursday 12 November to Thursday 19 November. Both access claims are shared. A103 waits on both A101 and A102. Do Mechanical A and Electrical A confirm they can work in the area together for those days?
8. **O2, Level 3 west: A104 and A105.** The scheduled dates do not overlap, but on reported dates the two trades share Thursday 12 November and Friday 13 November, 2 working days. No access claim is on file for A104. A105 and A109 wait on A104. Nothing waits on A105. Does A105 wait until A104 finishes, or do Framing A and Electrical A share the area for those 2 days?
9. **O3, Level 3 west: A105 and A109.** The two trades overlap for 6 working days, from Tuesday 17 November to Tuesday 24 November. Both hold exclusive access claims for the area (X1, X2), so the plans conflict. Nothing waits on either activity. Which plan for Level 3 west stands for those days, and which trade leads confirm capacity?
10. **O4, Level 2 east: A103 and A108.** The two trades overlap for 3 working days, from Monday 30 November to Wednesday 2 December. Both hold exclusive access claims for the area (X5, X6), so the plans conflict, and A108 waits on A103 (question 6). A111 waits on A108. Which plan for Level 2 east stands for those days, and which trade leads confirm capacity?

**APPROVED AS NOTED**

S05 Drywall board product data, for A103, submitted Wednesday 28 October. The notes are on the approval itself.

**NOTES THE REVIEW DOES NOT JUDGE**

None.

**LEFT OUT**

- A100 Level 2 east layout and marking: complete.
- A111 Level 2 east flooring: starts Monday 7 December, after the window ends.

Rows linked to left-out activities: 1.

**SUPPLIED BUT NOT LINKED**

- Delivery D06: fire-rated door frames, needed Friday 20 November, status not ordered. No activity named.
- Trade update U09: Plumbing A, reported Tuesday 10 November, start Wednesday 18 November to Friday 20 November, crew 2. Activity A120 is not on the schedule.

**DECISION OF THE SUPERINTENDENT (left blank for them)**

Sequencing: [ ] confirmed as listed   [ ] changed (note which activities)
Follow-up assigned on the lists above: [ ] yes   [ ] not yet
Capacity confirmed by the trade leads: [ ] yes   [ ] not yet
Name, role and date: ____________

Prepared for the Superintendent's meeting. No schedule has been changed, nothing has been sent, and no trade, supplier, designer or reviewer has been contacted.
