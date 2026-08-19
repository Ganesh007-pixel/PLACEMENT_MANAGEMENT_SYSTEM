# CRC Cards

One table per surviving class, drawn from `noun-analysis.md`.

## Specification 1: Placement Tracker System

### Class: Student

| Responsibilities | Collaborators |
|---|---|
| Register / log in to the system | — |
| Maintain own profile | StudentProfile |
| View job and internship opportunities | Job, Internship |
| Apply for a job | Job, Application |
| Apply for an internship | Internship, Application |
| Check own eligibility against criteria | EligibilityCriteria |
| View own application status | Application |

### Class: Recruiter

| Responsibilities | Collaborators |
|---|---|
| Post / manage job opportunities | Job |
| Define eligibility criteria for a job | EligibilityCriteria |
| Review submitted applications | Application |
| Update application status | Application |

### Class: TPO

| Responsibilities | Collaborators |
|---|---|
| Oversee the overall placement process | Student, Recruiter |
| Verify student eligibility | EligibilityCriteria, StudentProfile |
| Coordinate between recruiters and faculty | Recruiter, Faculty Coordinator |
| Monitor applications and outcomes | Application |

### Class: Faculty Coordinator

| Responsibilities | Collaborators |
|---|---|
| Coordinate placement activities for assigned students | Student |
| Monitor student eligibility / academic standing | EligibilityCriteria, StudentProfile |

### Class: StudentProfile

| Responsibilities | Collaborators |
|---|---|
| Store student's personal and academic details (name, branch, CGPA, etc.) | Student |
| Allow update by the owning student | Student |
| Supply data needed for eligibility checks | EligibilityCriteria |

### Class: Job

| Responsibilities | Collaborators |
|---|---|
| Store job opportunity details | Recruiter |
| Hold associated eligibility criteria | EligibilityCriteria |
| Receive and track applications | Application |

### Class: Internship

| Responsibilities | Collaborators |
|---|---|
| Store internship opportunity details | Recruiter |
| Hold associated eligibility criteria | EligibilityCriteria |
| Receive and track applications | Application |

### Class: Application

| Responsibilities | Collaborators |
|---|---|
| Represent a student's application to a Job or Internship | Student, Job, Internship |
| Track and update its own status | Recruiter |
| Report status back to the applying student | Student |

### Class: EligibilityCriteria

| Responsibilities | Collaborators |
|---|---|
| Define eligibility rules (e.g., minimum CGPA) for a Job/Internship | Job, Internship |
| Validate a student's eligibility against stored profile data | StudentProfile |
| Report eligibility result to Student / TPO / Faculty Coordinator | Student, TPO, Faculty Coordinator |

---

## Specification 2

*Not yet provided — add cards here once the second specification is shared.*

---

## Specification 3

*Not yet provided — add cards here once the third specification is shared.*
