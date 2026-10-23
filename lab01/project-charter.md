# Project charter: Realtime Quiz platform

| Field | Value |
|---|---|
| Version | 1.0 (draft for sponsor approval) |
| Date | 2026-09-29 |
| Sponsor | Head of the IT department |
| PM | Chheng Kimter, supervising lecturer |

## 1. Purpose and justification

Lecturers currently spend 1 to 2 hours every week manually marking paper-based quizzes while having no real-time visibility into student comprehension during lectures. The Realtime Quiz platform solves this problem by delivering a responsive web application that conducts live, synchronized classroom quizzes with automated instant scoring and an interactive leaderboard. Deploying this solution saves approximately 30 hours of grading effort per lecturer each academic year while substantially improving active student engagement in class. Developing this platform internally also avoids recurring third-party commercial SaaS subscription fees and keeps student performance data under departmental control. A comprehensive financial comparison and justification against commercial alternatives is detailed in business-case.md (Option C).

## 2. Objectives and success criteria

| # | Objective (what will be true) | Success criterion (number + week) |
|---|---|---|
| O1 | Working MVP demonstrated with all core Must features | 100% of Must features (authoring, live session, timer, scoring, leaderboard, accounts) demonstrated with 0 critical defects, week 7 |
| O2 | Pilot with 50 students in one live session | 50 participants, 0 blocking defects in one live session, week 14 |
| O3 | Broadcast latency during the pilot | <= 500 ms at the 95th percentile with 50 active participants, measured week 14 |
| O4 | System concurrency and load capacity under pressure | >= 100 concurrent student connections sustained with 0 dropped WebSocket sessions during stress testing, week 12 |
| O5 | Automated test coverage across codebase | >= 80% line coverage measured by JaCoCo in the continuous integration pipeline, week 13 |

## 3. High-level scope

In scope:
- Quiz authoring and management module (creating, editing, and organizing timed multiple-choice questions)
- Live synchronized quiz session runner with server-authoritative countdown timer
- Real-time answer submission processing, automated instant scoring engine, and live leaderboard display
- User account authentication and role-based access control for instructors and students
- Quiz session analytics dashboard with student result export in CSV and PDF formats
- Responsive web user interface supporting standard desktop and mobile browsers
- Automated deployment package and production operational runbook for Linux VPS

Out of scope:
- Native mobile applications for iOS and Android
- Learning Management System (LMS) integration via LTI standard (e.g., Moodle or Canvas gradebook sync)
- Free-text, open-ended, and automated essay question grading
- Multi-node clustering, Redis registry, and RabbitMQ distributed relay scaling
- Real-time student messaging, in-quiz chat rooms, and audio/video broadcasting

## 4. Milestones

| Week | Milestone | Ends process group |
|---|---|---|
| 1 | Charter approved, team formed | Initiating |
| 3 | Project management plan baselined | Planning |
| 4 | User accounts, security, and quiz authoring completed | Executing |
| 7 | MVP demo: live session, timer, scoring, and leaderboard | Executing |
| 10 | Session analytics, grade export, and notifications completed | Executing |
| 12 | System hardening: 100-student load test passed | Executing |
| 14 | Pilot with 50 students, closure and hand-over | Closing |

## 5. Budget summary

Effort: students 4 x 14 x 8 h = 448 h; PM 14 x 3 h = 42 h; total 490 h  
Cash: hosting 4 x 25 USD = 100; domain 15; tools 60; reserve 25 (14 %) total 200 USD

| Budget line | Calculation / Basis | Total |
|---|---|---|
| Student effort | 4 students x 14 weeks x 8 h/week | 448 person-hours |
| PM effort | 1 supervising lecturer x 14 weeks x 3 h/week | 42 person-hours |
| **Total Effort** | **448 h + 42 h** | **490 person-hours** |
| VPS hosting | 4 months x 25 USD/month (Linode VPS at gicitc.com) | 100 USD |
| Domain name | 1 domain registration for 1 year | 15 USD |
| Optional tools | Development utilities, UI assets, and monitoring services | 60 USD |
| Contingency reserve | 14.3% (~14%) of baseline cash lines (25 / 175 USD) | 25 USD |
| **Total Cash** | **100 + 15 + 60 + 25 USD** | **200 USD** |

## 6. Assumptions

- Four assigned software engineering students are available and committed to contribute 8 productive hours per week each throughout the 14-week semester.
- The IT department provides a dedicated Linode VPS instance at gicitc.com with root administrative access from week 2 onward.
- Campus Wi-Fi network and firewall policies permit persistent bidirectional WebSocket (STOMP) connections without filtering or throttling.
- Course instructors and at least 50 enrolled students are available to participate in the scheduled pilot session in week 14.

## 7. Constraints

- **Fixed schedule:** The project duration is strictly constrained to the 14-week university semester (commencing 2026-09-29) with no possibility of semester extension.
- **Budget cap:** Total cash expenditure cannot exceed the 200 USD cap, and effort must remain within the 490 person-hours allocated.
- **Data privacy and hosting:** All student identifiers and quiz records must remain on self-hosted departmental infrastructure at gicitc.com to comply with institutional data protection rules.
- **Platform compatibility:** The system must function reliably across modern standard web browsers without requiring proprietary client-side installations.

## 8. High-level risks

- **Real-time concurrency bottlenecks:** High concurrent traffic from 50 to 100 simultaneous answer submissions within a narrow 20-second window could cause message drops or server-side latency spikes exceeding 500 ms (Mitigation: conduct stress tests in week 12 and optimize in-memory state caching).
- **Scope creep:** Demands for non-core features (such as mobile apps or LMS grade sync) could threaten the fixed week 7 MVP and week 14 pilot dates (Mitigation: enforce strict scope control, freeze MVP scope at week 4, and track non-goals).
- **Campus network interference:** University proxy servers or firewalls might interrupt WebSocket handshakes during live lectures (Mitigation: implement early network testing in week 3 and provide fallback connection handling).

## 9. Project manager authority

- **Decides alone:**
  - Assigns tasks, technical roles, and pair-programming responsibilities among the four student team members.
  - Re-plans and adjusts the project schedule and activity sequencing within the 490 person-hour and 200 USD limits.
  - Selects internal technical design patterns, libraries, and tools covered by the 60 USD tools allocation.
  - Allocates from the 25 USD contingency reserve for unplanned infrastructure and hosting costs.
- **Needs sponsor approval:**
  - Any change to project scope (modifying Must/Should features or incorporating out-of-scope non-goals).
  - Any adjustment to major project milestones, including rescheduling the week 7 MVP demo or shifting the week 14 pilot date.
  - Any commitment of financial expenditure exceeding the approved 200 USD cash ceiling or requesting additional student hours.
  - Formal approval must be obtained in writing from the sponsor within 5 working days of request submission.

## 10. Approval

Sponsor: ____________________ Date: ________  
PM: ____________________ Date: ________
