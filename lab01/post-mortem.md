# Post-mortem: CampusPay wallet (2026)

This document provides a post-mortem analysis of the **CampusPay wallet** project failure using the foundational project management concepts from Chapter 01 (process groups, knowledge areas, organisational structures, success criteria, and PMI ethics). It concludes with five binding commitments for the Realtime Quiz project, directly traceable to our project charter.

---

## 1. Timeline and sources

| # | When | Event | Source |
|---|---|---|---|
| 1 | Month 1 (Feb) | University administration tasks IT unit with building a cashless payment application for canteen purchases and library fines within one semester. | Fictional case from Lab-01 |
| 2 | Month 2 (Mar) | Head of finance agrees to "sponsor" the project via email but provides no formal funding, approves no charter, and attends no reviews. | Fictional case from Lab-01 |
| 3 | Month 3 (Apr) | Lead developer is assigned as dual-role project manager and sole backend coder with no management authority or staff relief. | Fictional case from Lab-01 |
| 4 | Month 4 (May) | An informal campus survey leads to massive scope creep, adding campus bus ticketing and parking payments without schedule or budget adjustment. | Fictional case from Lab-01 |
| 5 | Month 5 (Aug) | Coding is completed against software emulators; zero integration tests are conducted with physical point-of-sale (POS) card terminals. | Fictional case from Lab-01 |
| 6 | Day 1 (Sep) | Public launch: live terminals reject 40% of payment attempts; canteen queue lengths double and student dissatisfaction spikes. | Fictional case from Lab-01 |
| 7 | Day 3 (Sep) | Following widespread cashier complaints and transaction reconciliation failures, management withdraws CampusPay from all locations. | Fictional case from Lab-01 |
| 8 | Month 10 (Feb) | CampusPay relaunches five months late after substantial rework, with scope forcefully scaled back to canteen payments only. | Fictional case from Lab-01 |

---

## 2. Classification and organisation

- **Project vs. Programme:** CampusPay was originally conceived as a single project (a temporary effort with a definite one-semester end date to create a unique cashless payment product). However, when bus ticketing and parking facilities were added, it effectively became an uncoordinated, unfunded programme composed of three distinct domain systems without the programme-level governance, stakeholder alignment, or integration benefits required.
- **Organisational Structure & PM Authority:** The project operated within a rigid **functional structure**. The lead developer was placed in the role of an expediter/coordinator with **virtually zero authority** over resources, priorities, or release readiness, while still carrying full coding responsibilities.
- **Sponsor, Charter, and PMO:** 
  - **Sponsor:** The project suffered from "phantom sponsorship." The Head of Finance agreed by email to the concept but never accepted accountability, signed no documents, and failed to attend reviews.
  - **Charter:** No project charter was ever written or signed; the team worked without defined scope boundaries, explicit authority limits, or signed success criteria.
  - **PMO:** There was no PMO oversight to enforce governance stage gates, provide estimation templates, or mandate independent quality verification.

---

## 3. Success criteria

- **Stated criteria:** The only stated criterion was a single, vague binary date milestone: *"Launch in September."*
- **Missing measurable criteria:**
  - *Technical reliability:* Payment transaction success rate $\ge 99.5\%$ under concurrent peak lunch hour load.
  - *Performance latency:* Transaction authorization latency $\le 2.0\text{ seconds}$ from terminal scan to receipt generation.
  - *Defect threshold:* Zero severity-1 (blocking) hardware or payment gateway defects on production POS hardware.
  - *Operational verification:* Passing an end-to-end dry-run of $\ge 200$ test payments across all physical canteen terminals prior to go-live.
- **Ignored wider dimensions of success:**
  - *Benefits realised:* No measurement of whether canteen transaction speed improved or whether administrative overhead was reduced.
  - *User satisfaction:* Canteen operators and students experienced acute frustration as lines doubled, damaging trust in university IT.
  - *Operational readiness:* Canteen cashiers received zero training, no terminal error runbooks were provided, and no offline cash fallback protocol existed.
  - *Team learning and health:* The developer suffered severe burnout from managing unrealistic expectations while writing untested code under pressure.

---

## 4. Process groups and knowledge areas

### What went wrong across the five process groups

| Process group | What went wrong or was skipped |
|---|---|
| **Initiating** | No project charter was created; the head of finance never formally accepted sponsor accountability, so nobody had the authority to refuse the bus-ticket and parking scope creep. |
| **Planning** | Rigorous planning was skipped entirely; the team created no WBS, no schedule network, no test strategy, and no risk register, relying instead on informal optimistic guesses. |
| **Executing** | Development was conducted in an isolated emulator bubble; the team never tested against real hardware card terminals, production network proxies, or live banking APIs. |
| **Monitoring and controlling** | Progress was reported as "on schedule" without a single end-to-end integration test, falling directly into Brooks' invisibility trap where critical defects remained hidden until day one. |
| **Closing** | No pilot, no formal user acceptance, and no controlled cut-over were conducted; the software failed immediately in production and was abandoned within three days without an orderly retrospective. |

### Three knowledge areas most responsible

1. **Integration Management (PMBOK Ch. 01 / 03):** There was no project charter to formally authorise work and no integrated change control mechanism. Decisions to add municipal bus ticketing and parking payments were made informally without evaluating impact on the immutable September launch deadline.
2. **Quality Management (PMBOK Ch. 07):** Quality assurance was entirely omitted. The team performed no integration testing with physical card hardware and no stress testing under simulated canteen peak volumes, deploying an untested artifact directly to production.
3. **Scope Management (PMBOK Ch. 04):** The project suffered catastrophic scope creep. Because the scope baseline was never decomposed into a Work Breakdown Structure (WBS) with clear non-goals, secondary desires from campus surveys bloated the deliverable beyond what could be built in one semester.

---

## 5. Ethics

### Decision examined
The decision by the lead developer and IT leadership to proceed with the public production launch on Day 1 in September despite knowing that **zero end-to-end transaction tests had ever been conducted on actual physical card terminals**.

### Evaluation against the PMI Code of Ethics and Professional Conduct

- **Responsibility:** **Breached.** Project leaders failed to own the foreseeable consequences of launching unverified software. Instead of taking ownership and postponing the launch to perform hardware tests, they shifted the failure risk onto frontline canteen workers and students.
- **Respect:** **Breached.** Deploying broken payment software showed disregard for the operational time, lunch breaks, and daily routines of thousands of campus staff and students who depended on a reliable canteen service.
- **Fairness:** **Breached.** The decision was fundamentally unfair to students, who were coerced into using a mandatory payment system that trapped their funds and caused transaction disputes without adequate warning or fallback recourse.
- **Honesty:** **Breached.** Reporting the project as "ready for September launch" was dishonest. It obscured the critical truth that terminal interoperability was completely unverified, violating the core professional duty to provide accurate, transparent status even under deadline pressure.

---

## 6. What our project will do differently

To ensure the **Realtime Quiz** platform achieves a successful outcome, the project team makes five concrete, measurable commitments. Every commitment is directly traceable to our approved project charter.

| # | Commitment (We will ...) | Measured by | By week | Charter line |
|:---:|---|---|:---:|---|
| 1 | **Hold a signed charter and maintain active sponsor stage-gate governance** | Formal sponsor signature on charter and recorded minutes with sponsor go/no-go decisions at gates | Week 1 & Week 7 | [project-charter.md](project-charter.md) Section 10 (Approval), Section 9 (Authority), Milestone Week 7 |
| 2 | **Strictly freeze core MVP scope and refuse undocumented features without written sponsor approval** | Change log with 0 unapproved features; 100% of Must features demonstrated in MVP demo with non-goals preserved | Week 4 & Week 7 | [project-charter.md](project-charter.md) Section 3 (Scope In/Out), Milestone Week 4 & 7 |
| 3 | **Execute live multi-user stress and concurrency load tests on campus infrastructure before pilot** | Load test report confirming $\ge 100$ concurrent student connections with 0 dropped WebSocket sessions and latency $\le 500\text{ ms}$ | Week 12 | [project-charter.md](project-charter.md) Objective O4 (Capacity), Objective O3 (Latency), Milestone Week 12 |
| 4 | **Conduct a bounded, real-user classroom pilot before handing over to operations** | Live session with 50 students completing a quiz with 0 blocking defects and instructor rating $\ge 4/5$ | Week 14 | [project-charter.md](project-charter.md) Objective O2 (Pilot), Objective O5, Milestone Week 14 |
| 5 | **Enforce automated CI quality gates with continuous test verification** | Automated JaCoCo code coverage report verifying $\ge 80\%$ line test coverage on every pull request | Week 13 | [project-charter.md](project-charter.md) Objective O5 (Coverage), Section 7 (Constraints) |
