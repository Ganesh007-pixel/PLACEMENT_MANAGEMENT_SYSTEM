# Noun–Verb Analysis — Specification 1: Placement Tracker System

*Source: Use Case Diagram — Placement Tracker System (actors, use cases, and external actors)*

## Step 1: Raw Candidate List

All nouns/noun phrases extracted from actor labels and use case names:

1. Student
2. Recruiter
3. Company HR
4. TPO
5. Placement Officer
6. Faculty Coordinator
7. Login
8. Register
9. Student Profile
10. Job Opportunities
11. Job
12. Application
13. Application Status
14. Internship
15. Eligibility Criteria
16. CGPA
17. Email
18. SMS
19. Scheduler
20. Placement Tracker System

## Step 2: Filters Applied

| # | Filter | Meaning |
|---|--------|---------|
| F1 | Redundant / Synonym | Duplicate concept already captured by another candidate |
| F2 | Vague / Out of scope | Names the system itself, or an external actor already modeled as an actor rather than a domain class |
| F3 | Attribute, not a class | Describes a property/value of another class rather than an entity with identity |
| F4 | Operation, not a class | Is actually a verb/action → becomes a responsibility (method), not a class |

## Step 3: Candidate Disposition

| Candidate | Verdict | Filter | Reasoning |
|---|---|---|---|
| Student | **Survives** | — | Primary actor with distinct data & behavior |
| Recruiter | **Survives** | — | Primary actor (posts jobs, reviews applications) |
| Company HR | Eliminated | F1 | Synonym/descriptor of Recruiter |
| TPO | **Survives** | — | Kept as the canonical class name |
| Placement Officer | Eliminated | F1 | Synonym of TPO — merged into TPO |
| Faculty Coordinator | **Survives** | — | Distinct primary actor with its own use cases |
| Login | Eliminated | F4 | Action performed by an actor → becomes a method (e.g. `Student.login()`) |
| Register | Eliminated | F4 | Action → becomes a method (e.g. `Student.register()`) |
| Student Profile | **Survives** | — | Holds student's own data, has identity, is updated independently |
| Job Opportunities | Eliminated | F1 | Plural/synonym of Job — merged into Job |
| Job | **Survives** | — | Core domain entity (posted by Recruiter, applied to by Student) |
| Application | **Survives** | — | Core domain entity linking Student to Job/Internship |
| Application Status | Eliminated | F3 | A status value/attribute *of* Application, not a class itself |
| Internship | **Survives** | — | Distinct opportunity type with its own use case (UC6) |
| Eligibility Criteria | **Survives** | — | Encapsulates rules (e.g., CGPA cutoff) used to validate applications |
| CGPA | Eliminated | F3 | Attribute of Student / used inside Eligibility Criteria, not a class |
| Email | Eliminated | F2 | Already modeled as the external actor "Email/SMS"; not a domain class |
| SMS | Eliminated | F2 | Same as Email — external actor, not a domain class |
| Scheduler | Eliminated | F2 | Time-triggered external actor, not a domain class |
| Placement Tracker System | Eliminated | F2 | Names the system boundary itself, not a class within it |

## Step 4: Surviving Classes

1. **Student**
2. **Recruiter**
3. **TPO**
4. **Faculty Coordinator**
5. **StudentProfile**
6. **Job**
7. **Application**
8. **Internship**
9. **EligibilityCriteria**

(Verbs eliminated by F4 — Login, Register, and additionally Update, View, Apply, Check from the use case names — are carried forward as candidate operations/responsibilities on the surviving classes; see CRC cards.)
