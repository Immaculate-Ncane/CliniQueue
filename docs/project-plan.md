# CliniQueue: Project plan

| | |
|---|---|
| **Project** | CliniQueue: offline clinic queue system |
| **Owner** | Sthembele Immaculate |
| **Type** | Self-assigned portfolio project |
| **Design phase** | 2025 (screens designed in Figma) |
| **Build phase** | 2026 (built in Java Swing with SQLite) |
| **Status** | In progress: core features complete |

## 1. Background
I grew up in Gcilima. When I went to the clinic, I registered in a very big paper register. A person at the front desk wrote down my name, ID number and reason for visiting. Then I sat with everyone else, who were going to different lines, watching people jump the queue and unsure which door I would be called to. This project is my attempt to make that experience faster and clearer for patients, front desk staff and nurses, with less paper, in areas where internet is unreliable.

## 2. Goal and objectives
**Goal:** build an offline queue system for rural clinics that registers patients and gives them a ticket with a queue number and room number.

**Objectives:**
1. Let patients register themselves at a kiosk, so the front desk no longer copies details into a paper register.
2. Give every patient a ticket with a queue number and a room number, so they know where to go.
3. Store tickets in a local database, so the queue is not lost during a power cut.
4. Work fully offline.
5. Give nurses a clear, ordered list of waiting patients (planned).

## 3. Deliverables
- CliniQueue desktop application (Java Swing, SQLite)
- Local SQLite database design
- Requirements document
- Test plan with results
- README and demo video on GitHub
- This project plan

## 4. Scope statement
**In scope (version 1):**
- Check-in and registration with validation (required fields, 13-digit ID, optional file number)
- Reason for visit: General Illness, Treatment and Chronic Med
- General Illness tickets generated from saved records and stored in the database
- Chronic Med and Wound Management ticket pages

**Out of scope for now:**
- Staff screen for calling the next patient
- Emergency fast-track
- HIV Services, Child and Pregnancy options
- Saving Chronic Med and Treatment tickets to the database
- Showing the file number on the Chronic Med ticket
- Ticket printing and isiZulu language option

## 5. Assumptions and constraints
- One developer, working alone while job hunting, so version 1 was kept small.
- The clinic has no reliable internet, so the system must work offline.
- Patient data is sensitive (POPIA), so only fake data is used for testing and no database file is published.
- This is a learning project. It is not in use at any clinic.

## 6. Stakeholders

| Stakeholder | Problem today | What CliniQueue does |
|---|---|---|
| Patients | Unclear lines, queue jumping, not knowing which door | Ticket with queue number and room number |
| Front desk staff | Writing every patient into a paper register | Patients register themselves |
| Nurses | No clear order of who is waiting | Ordered queue (staff screen planned) |
| Clinic management | Paper records are easily lost | Digital records stored locally |

## 7. Work breakdown and status

| # | Task | Status |
|---|------|--------|
| 1 | Design the screens | Done |
| 2 | Build screens and navigation in NetBeans | Done |
| 3 | Input validation (empty fields, 13-digit ID) | Done |
| 4 | Add SQLite and create the queue table | Done |
| 5 | Ticket numbers and saving (General Illness) | Done |
| 6 | Chronic Med and Wound Management ticket pages | Done |
| 7 | Publish to GitHub with README and demo video | Done |
| 8 | Requirements, database design and test plan | Done |
| 9 | Show file number on the Chronic Med ticket | Planned |
| 10 | Save Chronic Med and Treatment tickets | Planned |
| 11 | Staff screen (call next patient) | Planned |
| 12 | Emergency fast-track | Planned |

## 8. Resources
- **Tools:** NetBeans, Java, Maven, SQLite, DB Browser for SQLite, GitHub and GitHub Desktop, Figma
- **People:** one developer
- **Time:** (1 month and 1 week)

## 9. Risks

| Risk | Impact | Response |
|------|--------|----------|
| Power cuts | Queue data lost | Each ticket is saved to the database immediately |
| No internet | Cloud tools unusable | Offline design with a local SQLite file |
| Patient data published by mistake | Privacy breach (POPIA) | Database excluded from GitHub; fake data only |
| Limited time | Unfinished project | Kept version 1 small and listed extras as planned |

## 10. Success criteria
- A patient can register and receive a ticket without help from the front desk.
- Invalid input (empty fields, IDs that are not 13 digits) is rejected.
- Ticket numbers continue correctly after the app is closed and reopened.
- All tests in the test plan pass.

**Result so far:** (29 October 2026) all tests in the test plan passed.

## 11. Lessons learned
- A missing image path crashed a screen, so I learned to check file paths and the resources folder.
- A condition using `||` instead of `&&` showed an error every time, so I learned to test conditions with real inputs.
- A project inside OneDrive blocked the Maven build, so I learned to keep projects out of synced folders.
- A file committed before `.gitignore` existed stayed on GitHub, so I learned to set up `.gitignore` first.

## 12. Next milestones
1. Show the file number on the Chronic Med ticket
2. Build the staff screen for nurses
3. Save the remaining visit types to the database
