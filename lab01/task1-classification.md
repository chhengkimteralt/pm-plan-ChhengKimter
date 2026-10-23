# Task 1: project, operation or programme?

| # | Initiative | Temporary? | Unique? | Coordinated? | Class | Justification |
|---|------------|------------|---------|--------------|-------|---------------|
| 1 | Build the Realtime Quiz platform and pilot it with 50 students in week 14 | yes | yes | no | Project | It has a definite end date (week 14) and creates a unique, newly developed quiz platform tested with students. |
| 2 | Run the nightly backup of the gicitc.com PostgreSQL database | no | no | no | Operation | Repeats every night with the same output and no end date; it is part of keeping the service running. |
| 3 | Move the department's three web servers to a new Linode region before 15 December | yes | yes | no | Project | It is bound by a strict deadline (before 15 December) and achieves a one-off migration of web server infrastructure. |
| 4 | Answer helpdesk tickets within the 4-hour service level | no | no | no | Operation | It is an ongoing user support service without a definite end date that repetitively resolves tickets against a service level agreement. |
| 5 | "Digital classroom": Realtime Quiz, LMS upgrade and lecture capture sharing one login and one grade export | yes | yes | yes | Programme | Three related projects; the shared login and grade export are a benefit that none of them delivers alone, so they are coordinated. |
| 6 | Apply the monthly security patches to the VPS | no | no | no | Operation | It is a routine monthly maintenance task with no end date that keeps existing servers secure. |
| 7 | Add multi-node scaling (RabbitMQ relay, Redis registry) to Realtime Quiz next semester | yes | yes | no | Project | It has a defined timeframe (next semester) and delivers a unique architectural upgrade that does not yet exist. |
| 8 | Operate the Realtime Quiz platform after go-live: password resets, restarts, monitoring | no | no | no | Operation | It consists of ongoing, repetitive operational tasks with no end date to keep the live platform running. |
| 9 | Write and publish the department's annual IT report for the dean by 31 January | yes | yes | no | Project | It has a fixed deadline of 31 January and produces a unique annual document reflecting that specific year's performance. |
| 10 | Replace 40 wireless access points in two buildings during the summer break | yes | yes | no | Project | It is time-bounded by the summer break and achieves a one-time hardware replacement across two buildings. |

## Grey zones

- **Initiative 7 ("Add multi-node scaling... next semester"):** This can be viewed as an operation (a routine enhancement release or ongoing maintenance backlog item for an existing system) or as a project (a temporary effort with a distinct architectural deliverable). What would settle it is whether the sponsor formally authorises a dedicated budget and defines a specific scope with clear acceptance criteria for "done" (making it a project), or if it is absorbed into routine operational maintenance using existing department resources.
- **Initiative 9 ("Write and publish the department's annual IT report for the dean by 31 January"):** This can be viewed as an operation because it repeats every year as a recurring cyclical administrative obligation, or as a project because it has a firm deadline (31 January) and produces a unique deliverable based on new yearly data. What would settle it is who authorised the work and how time/budget are accounted: if staff write it as part of their routine ongoing duties it is an operation, whereas assigning a designated project lead with dedicated hours and a project charter makes it a small annual project.

## What our project hands over

At go-live in week 14, the Realtime Quiz project team hands over the platform to the department's IT operations and helpdesk support team to run day-to-day operations. The operations team will take responsibility for ongoing password resets, application restarts, routine monitoring, and incident response. To maintain the service reliably, they need comprehensive operational runbooks, deployment guides, monitoring credentials, and handover training from the project team.
