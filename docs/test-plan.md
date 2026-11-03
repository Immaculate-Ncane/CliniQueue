# CliniQueue: Test plan

**Tester:** Sthembele Immaculate
**Date tested:** (29 October 2026)
**Environment:** Windows, NetBeans, Java, SQLite

All tests use fake names and fake ID numbers only.

## Registration

| ID | Test | Input | Expected result | Actual result | Result |
|----|------|-------|-----------------|---------------|--------|
| T1 | Empty name | Leave name empty, fill the rest | Message "field can't be empty", stays on page |Pass |Pass |
| T2 | Empty surname | Leave surname empty | Message "field can't be empty" |Pass |Pass |
| T3 | Empty ID | Leave ID empty | Message "field can't be empty" | Pass|Pass |
| T4 | ID too short | 12 digits | Message "ID must be 13 numbers only" |Pass |Pass |
| T5 | ID too long | 14 digits | Message "ID must be 13 numbers only" |Pass |Pass |
| T6 | ID with letters | 12345abcde123 | Message "ID must be 13 numbers only" |Pass | Paa|
| T7 | Valid ID | 13 digits | Moves to Reason For Visit | Pass|Pass|
| T8 | File number left empty | Valid details, no file number | Moves on (file number is optional) |Pass |Pass |

## Reason for visit and tickets

| ID | Test | Steps | Expected result | Actual result | Result |
|----|------|-------|-----------------|---------------|--------|
| T9 | General Illness ticket | Register, click General Illness | Ticket page shows a ticket number (e.g. G001) and room 4 |Pass |Pass |
| T10 | Ticket saved | After T9, open cliniqueue.db in DB Browser | One new row with the same ticket number |Pass |Pass |
| T11 | Numbers increase | Repeat T9 with another fake patient | Next ticket number (e.g. G002), new row saved |Pass |Pass |
| T12 | Numbering after restart | Close the app, reopen, repeat T9 | Numbering continues, no restart from 001 |Pass |Pass |
| T13 | Chronic Med | Register, click Chronic Med | Opens the Chronic Med ticket page |Pass |Pass |
| T14 | Treatment list | Register, click Treatment | List of treatments is shown |Pass |Pass |
| T15 | Wound Management | From the list, click Wound Management | Opens its ticket page |Pass |Pass |
| T16 | Unavailable options | Click HIV Services, Child, Pregnancy, Emergency | Nothing opens (not built yet) |Pass |Pass |

## Navigation

| ID | Test | Steps | Expected result | Actual result | Result |
|----|------|-------|-----------------|---------------|--------|
| T17 | Back from Register | Click Back on the Register page | Returns to the welcome page |Pass |Pass |

## Known gaps (not tested yet)
- File number display on the Chronic Med ticket (not built)
- Saving Chronic Med and Treatment tickets to the database (not built)
- Staff screen and emergency fast-track (not built)

## Summary
All tests passed
