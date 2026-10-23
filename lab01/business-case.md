# Business case: live quizzes for the IT department

This document provides the financial and strategic justification for the Realtime Quiz project. It evaluates the current operational pain, compares three alternative investment options, models full life-cycle costs and benefits, calculates the payback period, and establishes a clear review gate.

## 1. Problem

Course instructors in the IT department spend an unsustainable amount of time manually administering and grading paper-based quizzes. Furthermore, paper quizzes provide no instantaneous feedback during class, preventing instructors from identifying student misunderstandings until days after a lecture has concluded. Students experience delayed feedback, reducing engagement and hindering active learning.

### Core assumptions:
- **Lecturers running quizzes:** 10 instructors across department courses
- **Marking time per lecturer per week:** 1 hour spent manually grading and recording paper quizzes
- **Teaching weeks per year:** 30 weeks (two 15-week academic semesters)
- **Notional value of one hour:** 10 USD/hour (used to objectively compare student and staff effort against commercial offerings; students are unpaid in cash)

### Quantified departmental burden:
- **Total annual faculty time lost:** $10 \text{ lecturers} \times 1 \text{ hour/week} \times 30 \text{ weeks} = 300 \text{ person-hours/year}$
- **Annual financial cost of lost time:** $300 \text{ hours} \times 10 \text{ USD/hour} = 3{,}000 \text{ USD/year}$

## 2. Options

### Option A: Do nothing (Paper quizzes & manual marking)
Maintain the status quo. Lecturers continue printing, distributing, collecting, and manually marking paper quizzes.
- **One-off cost:** 0 USD
- **Annual cost:** 0 USD direct cash expenditure (incurs ongoing 3,000 USD/year in lost faculty time)
- **Annual benefit:** 0 USD

### Option B: Buy commercial quiz SaaS (e.g., Kahoot! EDU Pro / Quizizz for Higher Ed)
Procure enterprise/higher-education subscriptions for cloud-hosted quiz software.
- *Market pricing citation / assumption:* Enterprise higher-ed plans (such as Kahoot! EDU Pro / Quizizz for Schools) typically cost between 12 USD and 18 USD per instructor per month. We assume an industry-standard rate of **15 USD per lecturer per month** (benchmark date: October 2026).
- **One-off cost:** 0 USD (cloud SaaS setup)
- **Annual cost:** $10 \text{ lecturers} \times 15 \text{ USD/month} \times 12 \text{ months} = 1{,}800 \text{ USD/year}$
- **Annual benefit:** Eliminates manual grading, saving 300 hours of lecturer time ($300 \text{ h} \times 10 \text{ USD/h} = 3{,}000 \text{ USD/year}$).

### Option C: Build Realtime Quiz in-house (Charter baseline)
Develop a custom, self-hosted web application using an internal team of 4 software engineering students (448 person-hours) and 1 supervising lecturer acting as PM (42 person-hours) over a 14-week semester.
- **One-off development cost:** $490 \text{ total person-hours} \times 10 \text{ USD/hour notional rate} = 4{,}900 \text{ USD}$ (complemented by 200 USD actual project cash for VPS, domain, tools, and contingency reserve).
- **Annual operational cost:** 1 Linux VPS at gicitc.com at 25 USD/month: $12 \times 25 \text{ USD} = 300 \text{ USD/year}$.
- **Annual gross benefit:** 3,000 USD/year (marking time saved) + 1,800 USD/year (avoided commercial SaaS licensing fees) = $4{,}800 \text{ USD/year}$.

| Option | Description | One-off cost | Annual cost | Annual benefit |
|---|---|:---:|:---:|:---:|
| A | Do nothing (manual paper marking) | 0 USD | 0 USD | 0 USD |
| B | Buy commercial SaaS (10 licenses @ 15 USD/mo) | 0 USD | 1,800 USD | 3,000 USD |
| C | Build Realtime Quiz (490 h @ 10 USD/h notional) | 4,900 USD | 300 USD | 4,800 USD |

## 3. Comparison

The payback period represents the time required for net operational cash and productivity gains to recover the initial investment outlay:
$$\text{Payback Period (years)} = \frac{\text{One-off Cost}}{\text{Net Annual Benefit}}$$

| Option | Net annual benefit | Payback (years) | Sensitivity (6 lecturers) |
|---|---|:---:|:---:|
| B | $3{,}000 - 1{,}800 = 1{,}200 \text{ USD}$ | 0 (no one-off cost) | $1{,}800 - 1{,}080 = 720 \text{ USD}$ (0 years) |
| C | $3{,}000 + 1{,}800 - 300 = 4{,}500 \text{ USD}$ | $\frac{4{,}900}{4{,}500} = 1.1 \text{ years}$ | $\text{Net benefit } 2{,}880 \text{ USD}: \frac{4{,}900}{2{,}880} = 1.7 \text{ years}$ |

*Detailed calculations are stored in [`business-case.csv`](file:///c:/Users/M/OneDrive/Documents/ITC/Year3_sem1/IT%20Project%20Management/Lab/pm-plan-ChhengKimter/lab01/business-case.csv).*

### Sensitivity analysis (6 lecturers scenario)
If only 6 instructors actively adopt the tool instead of 10:
- **Marking time saved:** $6 \times 1 \text{ h} \times 30 \text{ weeks} \times 10 \text{ USD} = 1{,}800 \text{ USD/year}$.
- **Option B SaaS cost:** $6 \times 15 \text{ USD} \times 12 \text{ months} = 1{,}080 \text{ USD/year}$. Net annual benefit drops to $1{,}800 - 1{,}080 = 720 \text{ USD/year}$.
- **Option C net annual benefit:** $1{,}800 \text{ (marking)} + 1{,}080 \text{ (avoided SaaS)} = 2{,}880 \text{ USD/year}$. The payback period extends slightly from 1.1 to **1.7 years**, remaining well within the department's 2-year capital return window.

## 4. Benefits not priced

1. **Student learning and curriculum value:** Designing, developing, and deploying a real-time distributed system provides 4 undergraduate students with invaluable capstone experience in WebSockets, system architecture, CI/CD, and project management.
2. **Institutional data ownership & privacy:** Student grades, attendance data, and quiz metrics remain strictly hosted on departmental infrastructure (gicitc.com), eliminating external cloud data processing risks and complying fully with institutional data protection standards.
3. **Zero per-seat licensing caps:** The self-hosted system imposes no arbitrary limits on student participant counts or class cohort sizes, avoiding the aggressive paywall tiers common to commercial platforms.
4. **Tailored departmental customization:** The codebase can be freely adapted and extended for programming tests, semester exams, and future integrations without vendor approval.

## 5. Risks per option

### Option A: Do nothing
1. **Ongoing productivity drain:** Lecturers continue losing 300 hours annually to low-value repetitive marking, leading to frustration and reduced time for research and mentoring.
2. **Pedagogical disadvantage:** Students receive no live interactive engagement during lectures, diminishing learning efficacy compared to peer institutions.

### Option B: Buy SaaS
1. **Vendor lock-in and pricing volatility:** Commercial SaaS vendors frequently restructure higher-education licensing tiers and impose annual price hikes that exceed departmental operating budgets.
2. **Privacy and compliance exposure:** Hosting sensitive student identification and performance records on multi-tenant overseas cloud infrastructure introduces regulatory and compliance risks.

### Option C: Build Realtime Quiz
1. **Delivery delay and schedule slip:** Architectural complexity (such as concurrency bottlenecks during WebSocket broadcasts or late answer submissions) could cause the team to miss the week 7 MVP demo or week 14 pilot.
2. **Operational maintenance overhead:** After student graduation, post-go-live bugs and system maintenance could place unexpected strain on IT operations if runbooks and code quality documentation are insufficient.

## 6. Recommendation and review gate

### Recommendation
**Proceed with Option C (Build Realtime Quiz).**  
Option C yields an outstanding net annual benefit of **4,500 USD/year** and achieves full capital payback within **1.1 years** (and **1.7 years** under conservative sensitivity modeling with only 6 lecturers). Beyond direct financial returns, Option C secures complete data sovereignty and delivers critical capstone educational outcomes for the department.

### Review gate (Week 7 MVP checkpoint)
In accordance with PRINCE2 principles of continued business justification, the project will undergo a formal stage-gate review at the **Week 7 MVP demonstration**:
- **Gate criteria:** The development team must demonstrate a functioning release containing 100% of Must features (quiz authoring, live synchronized session runner, timer, instant scoring, and live leaderboard) with 0 critical defects.
- **Contingency trigger:** If the week 7 MVP demonstration fails to meet these criteria and schedule recovery is not feasible within the budget reserve, the sponsor will immediately discontinue in-house development, procure **Option B (Buy SaaS)** for the following semester to guarantee teaching continuity, and re-scope the internal build as a multi-semester research initiative.
