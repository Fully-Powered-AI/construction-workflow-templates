# Submittal register review: an invented example

*Illustrative example with invented data.* The project, the trades, the submittals, the dates and every figure below are invented, and the trades are named Trade A to Trade H. The project is a small two-storey annex, called the Annex here. The project engineer runs the review on Monday 16 November 2026. People are referred to by role.

The inputs come first, in full, so the template can be run on them. The register follows.

## The inputs

### 1. Settings (typed by the project engineer)

```
Project: the Annex
Today: Monday 16 November 2026
Decides: the project engineer
```

The review period, the extra days for a resubmission and the long-lead threshold were not given, so the defaults are used: 14 days, 7 days and 56 days. Days are counted as calendar days.

### 2. Required submittals

```
submittal_no,spec_section,description,trade,required_documents
S-01,03 30 00,Concrete mix designs,Trade A,mix design report; test data
S-02,05 12 00,Structural steel shop drawings,Trade B,shop drawings; connection calculations; mill certificates
S-03,07 21 00,Roof insulation,Trade C,product data; samples
S-04,08 11 13,Hollow metal doors and frames,Trade D,product data; shop drawings; hardware schedule
S-05,23 73 00,Air handling units,Trade E,product data; shop drawings; performance data
S-06,26 24 16,Switchboards,Trade F,product data; shop drawings; coordination study
S-07,09 30 00,Floor tile,Trade G,product data; samples
S-08,14 21 00,Passenger elevator,Trade H,product data; shop drawings; cab finish samples
```

### 3. Submittal log

```
submittal_no,revision,received_date,documents_received,routed_to,routed_date,recorded_status,status_date,reviewer_comment,substitution
S-01,0,2026-10-12,mix design report; test data,Structural reviewer,2026-10-13,approved,2026-10-23,No comments,no
S-02,0,2026-10-05,shop drawings; connection calculations,Structural reviewer,2026-10-06,revise and resubmit,2026-10-27,See the marked drawings,no
S-02,1,2026-11-09,shop drawings; connection calculations; mill certificates,Structural reviewer,2026-11-10,with reviewer,,,no
S-03,0,2026-11-02,product data,,,received,,,yes
S-04,0,2026-10-26,product data; shop drawings; hardware schedule,Architect's reviewer,2026-10-27,with reviewer,,,no
S-05,0,2026-09-28,product data; shop drawings; performance data,Mechanical reviewer,2026-09-29,approved as noted,2026-10-19,See the marked copy,no
S-06,0,2026-11-12,product data; shop drawings,,,received,,,no
S-08,0,2026-09-14,product data; shop drawings,Architect's reviewer,2026-09-15,rejected,2026-10-09,Cab finish samples required with resubmission,no
S-09,0,2026-11-11,product data,Architect's reviewer,2026-11-12,with reviewer,,,no
```

### 4. Procurement dates

```
submittal_no,order_by_date,lead_time_days
S-01,2026-11-20,14
S-02,2026-12-14,70
S-03,2026-12-07,35
S-04,2026-11-27,42
S-05,2026-12-21,98
S-06,2026-12-02,112
S-07,2026-11-23,28
S-08,2027-01-11,168
```

## The output

**SUBMITTAL REGISTER REVIEW: the Annex, Monday 16 November 2026**

For: the project engineer. Prepared Monday 16 November 2026 from: required submittals (8 rows), submittal log (9 rows), procurement dates (8 rows), settings.  
Column check: all headers matched.  
Settings: review period 14 days, resubmission 7 days, long-lead threshold 56 days, counted in calendar days. Defaults used: review period, resubmission days, long-lead threshold.  
Summary: 8 required submittals. Accepted 2 (approved 1, approved as noted 1). With reviewer 2. Received, not with reviewer 2. Returned 1. Not received 1. Submittals with missing documents: 4 (received 3, not received 1). Routing to verify: 4. Long-lead not yet accepted: 3, of which 1 at risk. At risk before the order date: 3; past the order date: 0. Substitutions requested and not accepted: 1.

**Data checks**

- S-09 is in the submittal log and not on the required list. Left out of the register.

**Register**

- **S-01** 03 30 00 Concrete mix designs, Trade A. Revision 0 received Monday 12 October 2026. ACCEPTED: approved, recorded Friday 23 October 2026. Documents complete. Reviewer comment: "No comments".
- **S-02** 05 12 00 Structural steel shop drawings, Trade B. Revision 1 received Monday 9 November 2026. WITH REVIEWER since Tuesday 10 November 2026 (Structural reviewer), 6 days. Documents complete. Earlier revisions: revision 0 revise and resubmit, recorded Tuesday 27 October 2026. Long-lead, 70 days. Order by Monday 14 December 2026, 28 days away; review needs 14 days; 14 spare days.
- **S-03** 07 21 00 Roof insulation, Trade C. Revision 0 received Monday 2 November 2026. RECEIVED. Documents missing 1 of 2. Substitution requested. Order by Monday 7 December 2026, 21 days away; review and resubmission need 21 days; 0 spare days.
- **S-04** 08 11 13 Hollow metal doors and frames, Trade D. Revision 0 received Monday 26 October 2026. WITH REVIEWER since Tuesday 27 October 2026 (Architect's reviewer), 20 days. Documents complete. Order by Friday 27 November 2026, 11 days away; review needs 14 days; AT RISK, short 3 days.
- **S-05** 23 73 00 Air handling units, Trade E. Revision 0 received Monday 28 September 2026. ACCEPTED: approved as noted, recorded Monday 19 October 2026. Documents complete. Reviewer comment: "See the marked copy".
- **S-06** 26 24 16 Switchboards, Trade F. Revision 0 received Thursday 12 November 2026. RECEIVED. Documents missing 1 of 3. Long-lead, 112 days. Order by Wednesday 2 December 2026, 16 days away; review and resubmission need 21 days; AT RISK, short 5 days.
- **S-07** 09 30 00 Floor tile, Trade G. NOT RECEIVED. Documents missing 2 of 2. Order by Monday 23 November 2026, 7 days away; review and resubmission need 21 days; AT RISK, short 14 days.
- **S-08** 14 21 00 Passenger elevator, Trade H. Revision 0 received Monday 14 September 2026. RETURNED: rejected, recorded Friday 9 October 2026. Documents missing 1 of 3. Reviewer comment: "Cab finish samples required with resubmission". Long-lead, 168 days. Order by Monday 11 January 2027, 56 days away; review and resubmission need 21 days; 35 spare days.

**Missing documents**

- S-03 (Trade C): samples.
- S-06 (Trade F): coordination study.
- S-07 (Trade G): product data; samples. Nothing received.
- S-08 (Trade H): cab finish samples.

**Routing to verify**

- S-03: received Monday 2 November 2026, no reviewer recorded, 14 days.
- S-04: with the Architect's reviewer since Tuesday 27 October 2026, 20 days; 6 days over the 14-day review period.
- S-06: received Thursday 12 November 2026, no reviewer recorded, 4 days.
- S-08: returned Friday 9 October 2026; no newer revision received, 38 days. The log does not show whether the return reached the trade.

**Long-lead items not yet accepted: 3**

- S-06 Switchboards: AT RISK, short 5 days (order by Wednesday 2 December 2026). Not routed; coordination study missing.
- S-02 Structural steel shop drawings: 14 spare days (order by Monday 14 December 2026). With reviewer, 6 days.
- S-08 Passenger elevator: 35 spare days (order by Monday 11 January 2027). Returned; no resubmission.

**At risk before the order date: 3**

- S-07 Floor tile: short 14 days; order by Monday 23 November 2026.
- S-06 Switchboards: short 5 days; order by Wednesday 2 December 2026.
- S-04 Hollow metal doors and frames: short 3 days; order by Friday 27 November 2026.

**Questions for the project engineer**

1. S-03 Roof insulation (Trade C). Revision 0 arrived Monday 2 November 2026 with product data and no samples, and no reviewer is recorded after 14 days. A substitution is marked as requested. The order date is Monday 7 December 2026, 21 days away against 21 days needed, 0 spare. What do you want done about routing and the missing samples?
2. S-04 Hollow metal doors and frames (Trade D). With the Architect's reviewer for 20 days, 6 past the 14-day period; no decision recorded. The order date is Friday 27 November 2026, 11 days away against 14 days needed, short 3 days. What do you want done about the time left?
3. S-06 Switchboards (Trade F). Received Thursday 12 November 2026 without the coordination study, no reviewer recorded, 4 days. Long-lead, 112 days. The order date is Wednesday 2 December 2026, 16 days away against 21 days needed, short 5 days. What do you want done about routing and the missing study?
4. S-07 Floor tile (Trade G). No package has been received; product data and samples are missing. The order date is Monday 23 November 2026, 7 days away against 21 days needed, short 14 days. What do you want done about the missing package?
5. S-08 Passenger elevator (Trade H). Rejected Friday 9 October 2026 with the comment "Cab finish samples required with resubmission"; no resubmission in 38 days, and the log does not show whether the return reached the trade. Long-lead, 168 days. The order date is Monday 11 January 2027, 56 days away against 21 days needed, 35 spare. What do you want done about the resubmission?

Acceptance of each submittal rests with the authorized design reviewer. Nothing here accepts a material, and releasing an order is purchasing's decision.

Draft for the project engineer's decisions. No trade, reviewer or supplier has been contacted, and no log, status or order has been changed.
