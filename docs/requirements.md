# CliniQueue: Requirements

## Problem statement
Many rural clinics in South Africa have long, unstructured waiting lines and unreliable or no internet access. Patients do not know when they will be seen, and staff have no dependable record of who arrived first or why they came. Paper-based queues are easily lost, and cloud-based systems do not work when connectivity fails.

## Proposed solution
CliniQueue is an offline kiosk application that lets a patient check in, register, choose a reason for visit and receive a ticket with a queue number and room number. Queue data is saved to a local database so it survives power cuts.

> **Note:** this is a learning project and a design concept for a clinic setting. It is not a production medical system and is not in use at any clinic.

## How the app works today
1. **Check-In:** the patient starts at the welcome screen.
2. **Register:** the patient enters name, surname and ID number. A file number field is optional, because not every patient has a file at the clinic.
3. **Reason for visit:** three options currently work: General Illness, Treatment and Chronic Med.
4. **General Illness:** opens a ticket with a number generated from saved records, and the ticket is saved to the database.
5. **Treatment:** opens a list of treatments (Wound Management, Basic Trauma Care, Injection & Clinical). Only Wound Management works, and it opens a ticket page.
6. **Chronic Med:** opens a ticket page directly. The file number entered at registration is meant to identify the patient on the ticket, but it is not displayed yet.

## Functional requirements

| ID | Requirement | Status | Notes |
|----|-------------|--------|-------|
| F1 | Patient can start check-in from a welcome screen | Done | |
| F2 | Patient registers with name, surname and ID number | Done | |
| F3 | Registration has an optional file number field | Done | Field exists |
| F4 | System rejects empty fields and any ID that is not exactly 13 digits | Done | |
| F5 | Patient selects a reason for visit | Partial | 3 of 7 buttons work |
| F6 | System generates a ticket number from saved records (e.g. G004) | Done | General Illness only |
| F7 | System saves each ticket to a local SQLite database | Done | General Illness only |
| F8 | Ticket shows queue number and room number | Done | General Illness only |
| F9 | Treatment patients choose a treatment type | Partial | Only Wound Management works; not yet saved to the database |
| F10 | Chronic Med ticket shows the patient's file number | Partial | Ticket opens; file number not shown yet |
| F11 | Staff can view the waiting list and call the next patient | Planned | |
| F12 | Emergency patients are fast-tracked without full registration | Planned | |
| F13 | HIV Services, Child and Pregnancy reasons open a ticket | Planned | Buttons not active yet |

## Non-functional requirements

| ID | Requirement |
|----|-------------|
| N1 | Works fully offline, with no internet needed |
| N2 | Large buttons, colours and icons for low-literacy users |
| N3 | Tickets are saved immediately, so a power cut does not lose the queue |
| N4 | Database uses prepared statements to prevent SQL injection |
| N5 | Patient data stays on the local machine and is not published (POPIA) |

## Status summary
- **Done:** 7 of 13 functional requirements
- **Partial:** 3 of 13
- **Planned:** 3 of 13
