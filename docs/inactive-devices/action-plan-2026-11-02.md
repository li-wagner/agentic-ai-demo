# Inactive Device Action Plan, 02-Nov-2026

Proposals only. No action taken. Generated from the five files in `data/` under the rules in `CLAUDE.md`. Reviewed by the action-reviewer agent. A human decides and acts.


**Report date:** 02-Nov-2026 (from `reportDate`)
**Scope:** 15 tickets in `data/remediation_tickets.csv`
**Status:** Proposals only. No action has been taken. A human decides and acts.

Evidence uses data-row numbers (row 1 = first data row after the header).

| Device | User | Finding | Proposed action | Evidence | Irreversible | Confidence |
|---|---|---|---|---|---|---|
| NW-5KQ2MX3 | daniel.weber@northwind.example | Terminated; device returned (Step 2) | RESET AND CLOSE | asset_register.csv row 1 (Returned); offboarding_log.csv row 1 (laptop_returned Yes); entra_users.csv row 1 | No | High |
| NW-H8TV2N3 | sarah.collins@northwind.example | Terminated; device not returned; 38 days since last working day (2026-09-25) (Step 2) | REPORT LOST + REMOTE WIPE | offboarding_log.csv row 2 (laptop_returned No); asset_register.csv row 2 (In Use); entra_users.csv row 2 | Yes | High |
| NW-7RN4DK3 | julien.bernard@northwind.example | Terminated; device not returned; 21 days since last working day (2026-10-12) (Step 2) | FOLLOW UP ON RETURN | offboarding_log.csv row 3 (laptop_returned No); asset_register.csv row 3 (In Use); entra_users.csv row 3 | No | High |
| NW-PF3XQ8WD | emma.lindqvist@northwind.example | Terminated; device not returned; garden leave ends 2026-12-18 (future) (Step 2) | NO ACTION YET. Earliest further action: 2027-01-17 | offboarding_log.csv row 4 (garden_leave_end 2026-12-18); asset_register.csv row 4 (In Use); entra_users.csv row 4 | No | High |
| NW-9LM4RC3 | kofi.mensah@northwind.example | Active; ExtAtt9 is a leave value (Step 3) | NO ACTION: LEAVE FLAG ALREADY SET. HR to confirm leave end date | entra_users.csv row 5 (Leave of absence); asset_register.csv row 5 (In Use) | No | High |
| NW-PF4A7ZKH | hannah.novak@northwind.example | Active; account disabled; ExtAtt9 "Disabled after 30 days of inactivity" (Step 3) | CHECK STATUS WITH HR. Do not contact user. Do not re-enable account | entra_users.csv row 6 (accountEnabled FALSE; ExtAtt9 Disabled after 30 days of inactivity); asset_register.csv row 6 (In Use) | No | High |
| NW-3DJ6PW3 | raj.iyer@northwind.example | Active; another In Use device exists (8VN1QK3); this old device is In stock (Step 3) | RESET OLD DEVICE | asset_register.csv row 7 (In stock, replaced by 8VN1QK3); asset_register.csv row 16 (8VN1QK3 In Use, replacement for 3DJ6PW3); entra_users.csv row 7 | No | High |
| NW-D3HB6X3 | mei.chen@northwind.example | Active; another In Use device exists (K9QW2M3); old device In Use, not returned (Step 3) | CONTACT USER FOR RETURN | asset_register.csv row 8 (In Use; return pending); asset_register.csv row 17 (K9QW2M3 In Use, replacement for D3HB6X3); entra_users.csv row 8 | No | High |
| NW-2HR9ST3 | oliver.grant@northwind.example | Active; one In Use device; no leave flag; account enabled (Step 3) | CONTACT USER TO SYNC | entra_users.csv row 9; asset_register.csv row 9 (In Use) | No | High |
| NW-BX7K5Y3 | lucia.ferreira@northwind.example | Offboarding log and asset register disagree on return: log says returned (Yes), register says In Use (Step 1) | NEEDS HUMAN REVIEW: DATA CONFLICT | offboarding_log.csv row 5 (laptop_returned Yes); asset_register.csv row 10 (In Use); entra_users.csv row 10 | No | High |
| NW-PF58NGE2 | tomasz.wrobel@northwind.example | Terminated contractor; account still enabled; no offboarding record (Step 1) | ESCALATE: MISSED OFFBOARDING. Security risk. No other action proposed | entra_users.csv row 11 (accountEnabled TRUE; Terminated; Contractor); offboarding_log.csv: no row for this user | No | High |
| NW-6TC3WB3 | grace.adeyemi@northwind.example | Terminated contractor; account disabled; ExtAtt9 "Disabled after 30 days of inactivity"; no offboarding record (Step 1) | ESCALATE: MISSED OFFBOARDING (auto-disabled, not offboarded). No other action proposed | entra_users.csv row 12 (ExtAtt9 Disabled after 30 days of inactivity; Contractor); offboarding_log.csv: no row for this user | No | High |
| NW-JW2P8D3 | nikolai.petrov@northwind.example | Terminated contractor; account disabled; ExtAtt9 empty; no offboarding record (Step 1) | NEEDS HUMAN REVIEW: DATA CONFLICT | entra_users.csv row 13 (ExtAtt9 empty; Contractor); offboarding_log.csv: no row for this user | No | High |
| NW-PF2GM6XA | priya.nair@northwind.example | Out of scope: no INACTIVE issue; 0 days since check-in (Step 0) | NEEDS HUMAN REVIEW: NOT INACTIVE | remediation_tickets.csv row 14 (issues: SECURITY PATCHING) | No | High |
| USSANTOSD (4MZ8LH3) | diego.santos@northwind.example | Out of scope: no INACTIVE issue; unsupported Windows 22H2 (Step 0) | NEEDS HUMAN REVIEW: NOT INACTIVE | remediation_tickets.csv row 15 (issues: UNSUPPORTED WINDOWS VERSION) | No | High |

## Summary by proposed action

| Proposed action | Devices |
|---|---|
| REPORT LOST + REMOTE WIPE | 1 |
| RESET AND CLOSE | 1 |
| RESET OLD DEVICE | 1 |
| FOLLOW UP ON RETURN | 1 |
| CONTACT USER FOR RETURN | 1 |
| CONTACT USER TO SYNC | 1 |
| CHECK STATUS WITH HR | 1 |
| NO ACTION: LEAVE FLAG ALREADY SET | 1 |
| NO ACTION YET | 1 |
| ESCALATE: MISSED OFFBOARDING | 2 |
| NEEDS HUMAN REVIEW: DATA CONFLICT | 3 |
| NEEDS HUMAN REVIEW: NOT INACTIVE | 2 |

## Decisions needed from a human

Irreversible first.

1. **Remote wipe, NW-H8TV2N3 (Sarah Collins).** Approve or reject. The device has not been returned and is 38 days past the last working day. A wipe cannot be undone.
2. **Missed offboarding, NW-PF58NGE2 (Tomasz Wrobel), NW-6TC3WB3 (Grace Adeyemi).** Both are terminated contractors with enabled or auto-disabled accounts and no offboarding record. Confirm the account state and start the offboarding process. This is a security risk.
3. **Data conflicts, NW-BX7K5Y3 (Lucia Ferreira), NW-JW2P8D3 (Nikolai Petrov).** Decide which source is correct: the offboarding log or the asset register for Lucia, and HR status for Nikolai.
4. **HR check, NW-PF4A7ZKH (Hannah Novak).** HR to confirm her actual status. Do not contact the user and do not re-enable the account until HR responds.
5. **Leave end date, NW-9LM4RC3 (Kofi Mensah).** HR to confirm the leave end date. The export has none.
6. **Garden leave, NW-PF3XQ8WD (Emma Lindqvist).** Diary the earliest further action date, 2027-01-17.
7. **Out-of-scope tickets, NW-PF2GM6XA (Priya Nair), USSANTOSD (Diego Santos).** Confirm they belong to another workflow (patching or OS upgrade).
8. **Reset, NW-5KQ2MX3 (Daniel Weber) and NW-3DJ6PW3 (Raj Iyer).** Approve the reset. For Raj, confirm the physical device is not still with him, because Intune shows sign-ins through 10/09/2026 while the register says In stock.
9. **Return and sync, NW-7RN4DK3 (Julien Bernard), NW-D3HB6X3 (Mei Chen), NW-2HR9ST3 (Oliver Grant).** Approve outreach to the users. Mei's old device is marked "return pending," which is not a return.

---


Reviewer: action-reviewer agent. Checked all 15 tickets against the five files in `data/` and the rules in `CLAUDE.md`. Report date 02-Nov-2026. Row numbers are data rows (row 1 = first row after the header).

| Device | Plan says | Verdict | Rule applied (CLAUDE.md) | Reason |
|---|---|---|---|---|
| NW-5KQ2MX3 | RESET AND CLOSE | AGREE | L57: device Returned or In stock → RESET AND CLOSE | Entra row 1 Terminated, disabled. Offboarding row 1 Yes; register row 1 Returned 2026-09-24. Sources agree. |
| NW-H8TV2N3 | REPORT LOST + REMOTE WIPE | AGREE | L64-65: more than 30 days → REPORT LOST + REMOTE WIPE (irreversible) | Last working day 2026-09-25, 38 days ago. Offboarding row 2 No; register row 2 In Use. Minor: Intune row 2 last sign-in 9/26/2026, one day after last working day. Does not change the rule; a human should know before approving the wipe. |
| NW-7RN4DK3 | FOLLOW UP ON RETURN | AGREE | L62-63: 30 days or less → FOLLOW UP ON RETURN | Last working day 2026-10-12, 21 days ago. Offboarding row 3 No; register row 3 In Use. |
| NW-PF3XQ8WD | NO ACTION YET, earliest further action 2027-01-17 | DISPUTE | L59-61: garden leave in future → NO ACTION YET; state earliest date further action is allowed | NO ACTION YET is correct (garden leave ends 2026-12-18, offboarding row 4). The date is disputed: under L62-63 follow-up is allowed once garden leave ends, so the earliest follow-up is 2026-12-19. REPORT LOST and wipe need more than 30 days (L64), so the earliest date for those is 2027-01-18. The plan's 2027-01-17 is day 30, still a follow-up day. |
| NW-9LM4RC3 | NO ACTION: LEAVE FLAG ALREADY SET | AGREE | L68-70: leave value in ExtAtt9 → NO ACTION: LEAVE FLAG ALREADY SET | Entra row 5 Active, Leave of absence, no offboarding row. Gap: Entra row 5 shows the account disabled (FALSE). The finding should say so (L78-79). |
| NW-PF4A7ZKH | CHECK STATUS WITH HR | AGREE | L71-73: account disabled and ExtAtt9 not a leave value → CHECK STATUS WITH HR | Entra row 6 Active, FALSE, "Disabled after 30 days of inactivity". Plan correctly says do not re-enable. |
| NW-3DJ6PW3 | RESET OLD DEVICE | AGREE | L74-75: other In Use device exists; old device In stock → RESET OLD DEVICE | Register row 7 In stock 2026-10-19; register row 16 8VN1QK3 In Use. Entra row 7 Active, enabled. Error in plan decision item 8: it says Intune shows sign-ins through "10/09/2026". Intune row 7 shows 9/10/2026, before the In stock date, so the concern as written does not hold. Correct the text. |
| NW-D3HB6X3 | CONTACT USER FOR RETURN | AGREE | L74, L76: old device not returned → CONTACT USER FOR RETURN | Register row 8 In Use, "return pending"; register row 17 K9QW2M3 In Use. Entra row 8 Active, enabled. |
| NW-2HR9ST3 | CONTACT USER TO SYNC | AGREE | L77: otherwise → CONTACT USER TO SYNC | Entra row 9 Active, enabled, ExtAtt9 empty. One device in register (row 9, In Use). No offboarding row. |
| NW-BX7K5Y3 | NEEDS HUMAN REVIEW: DATA CONFLICT | AGREE | L53-54: offboarding log and asset register disagree on return → DATA CONFLICT | Offboarding row 5 Yes; register row 10 In Use. |
| NW-PF58NGE2 | ESCALATE: MISSED OFFBOARDING | AGREE | L42: ExtAtt7 Terminated and account enabled → ESCALATE: MISSED OFFBOARDING | Entra row 11 Terminated, TRUE, Contractor. No offboarding row. |
| NW-6TC3WB3 | ESCALATE: MISSED OFFBOARDING | AGREE | L45-46: Terminated, disabled, ExtAtt9 "Disabled after 30 days of inactivity", no offboarding row → ESCALATE | Entra row 12 matches all conditions. No offboarding row. |
| NW-JW2P8D3 | NEEDS HUMAN REVIEW: DATA CONFLICT | AGREE | L49-50: Terminated, disabled, ExtAtt9 empty, no offboarding row → DATA CONFLICT | Entra row 13 Terminated, FALSE, ExtAtt9 empty. No offboarding row. |
| NW-PF2GM6XA | NEEDS HUMAN REVIEW: NOT INACTIVE | AGREE | L36-37: no INACTIVE issue or under 30 days → NOT INACTIVE | Ticket row 14: SECURITY PATCHING only, 0 days. |
| USSANTOSD (4MZ8LH3) | NEEDS HUMAN REVIEW: NOT INACTIVE | AGREE | L36-37 | Ticket row 15: UNSUPPORTED WINDOWS VERSION, 1 day. Device name does not follow the NW- pattern; does not affect scope. |

Items to fix without changing any verdict:
- NW-9LM4RC3: state that the account is disabled (L78-79).
- Decision item 8: Raj Iyer's Intune sign-in is 9/10/2026, not 10/09/2026.

Agree: 14, Dispute: 1, Escalate: 0
