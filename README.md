# UAP Project 21 – Placement Drive Management

## 📌 Project Overview

**UAP_Project21_PlacementDriveManagement-R** is a **Placement Drive Management System** designed to streamline the recruitment process between **Colleges, Companies, Students, and Administrators**.

The system manages the complete placement lifecycle, starting from college and company registration, job requests, student applications, placement drive scheduling, interview evaluation, and final selection.

The project aims to reduce manual placement activities and provide a centralized platform for managing recruitment-related information and communication.

---

## 👥 Team Details

**Team Number:** 01
**Team Name:** Lads

### Team Members

| Role         | Name          |
| ------------ | ------------- |
| Team Lead    | Abdul Sathar  |
| Scrum Master | Dharunesh     |
| Team Member  | Lokesh Suriya |
| Team Member  | ShanmugaPriya |

---

# 🎯 Project Objective

The main objective of this project is to develop a centralized **Placement Drive Management System** that enables:

* Colleges to register and manage student information.
* Companies to register and request candidates for job openings.
* Companies to post job opportunities.
* Colleges to apply for available jobs.
* Colleges to upload eligible student details through Excel.
* Companies to schedule placement drives.
* Interview panels to evaluate candidates.
* Students to track their application and selection status.
* Automated communication through email.
* Administrators to approve or reject college and company registrations.

---

# 🏗️ Major Modules

## MLP01 – College & Company Registration

### 🏢 Company Registration

Companies can register on the platform by providing:

* Company Name
* CIN / Registration Number
* Sector
* Domain / Product
* Location
* Years of Experience
* Current Employee Count
* Previous Year's Profit
* Official Email ID

### Company Registration Flow

```text
Company Registration
        ↓
Submit Registration Request
        ↓
Admin Verification
        ↓
Approved / Rejected
        ↓
Company Login Credentials
```

Rejected applications will also be retained in the system with an appropriate **status**.

### 🏫 College Registration

Colleges can register by providing:

* College Name
* College Code
* Affiliation
* Location
* Years of Experience
* Student Count
* Placement Percentage
* NAAC Accreditation
* College Tier
* Official Email ID

### College Registration Flow

```text
College Registration
        ↓
Submit Registration Request
        ↓
Admin Verification
        ↓
Approved / Rejected
        ↓
College Login Credentials
```

Both **Company** and **College** data types maintain a registration **status** such as:

```text
Pending
Approved
Rejected
```

---

# 👨‍🎓 Student Registration

The student registration process is divided into multiple steps to make the registration clear and structured.

### Registration Flow

**Step 1 – Personal Details**

Collect student personal information.

**Step 2 – Academic Details**

Collect academic qualifications and placement-related information.

**Step 3 – Resume Upload**

Students upload their latest resume.

**Step 4 – Document Upload**

Students upload the required supporting documents.

**Step 5 – OTP Validation**

Verify the student's email/mobile using OTP validation.

**Step 6 – Terms & Conditions**

Student accepts the terms and conditions.

**Step 7 – Confirmation Email**

A confirmation email is sent to the student.

### College Approval

After student registration:

```text
Student Registration
        ↓
College Verification
        ↓
College Approval
        ↓
Student Account Activated
```

---

# 💼 MLP02 – Job Request & Recruitment Management

The Recruitment Management module handles the complete job and placement drive process.

The major services are:

1. **Post Job**
2. **Schedule Interview**
3. **Conduct Interview**
4. **HR Interview**

---

## 📢 Post Job

Companies can create job requests with details such as:

* Job ID
* Job Title
* Job Description
* Number of Openings
* Required Skills
* CTC
* Eligibility Criteria
* Company Details

### Job Status

```text
Open
Closed
```

The system also maintains the **number of students selected** for each job.

### Job Flow

```text
Company
   ↓
Post Job
   ↓
Job Request
   ↓
College Views Job
   ↓
College Applies
```

The **drive date is not required while posting a job**.

---

# 🏫 College Job Application

After a job is requested/posted, eligible colleges can view the job details.

Once a college selects a job, it must upload the details of eligible students.

### Student Application Data

The application should maintain information such as:

* College
* Student ID
* Student Name
* Gender
* Contact Number
* Email ID
* Job ID
* Company
* Job Status

Example:

| College     | Student ID | Name      | Gender | Contact | Email                                         | Job ID | Company | Job Status |
| ----------- | ---------- | --------- | ------ | ------- | --------------------------------------------- | ------ | ------- | ---------- |
| ABC College | S001       | Student 1 | M      | XXXXX   | [student@email.com](mailto:student@email.com) | J001   | TCS     | Applied    |

---

# 📊 Excel Student Upload

Colleges should be able to upload eligible student information using an **Excel file**.

### Proposed Flow

```text
College Login
      ↓
Select Job
      ↓
View Eligibility Requirements
      ↓
Upload Student Excel File
      ↓
Validate Excel Data
      ↓
Store Student Records
      ↓
Create Job Applications
```

The team will evaluate suitable approaches/tools for importing Excel data into the database.

---

# 📅 Schedule Interview

The company/recruitment team can schedule an interview for a college's job request.

### Process

```text
Company Login
      ↓
View College Job Requests
      ↓
Select Request
      ↓
Schedule Interview
```

The scheduling form contains:

* Drive Date
* Facilities Required
* Drive Mode
* Reporting Time
* Location / Meeting Link
* Candidate-wise timings where applicable

### Drive Mode

#### 🏢 Offline

For offline drives, the system should capture:

* College Address OR
* Company Address
* Drive Date
* Reporting Time
* Facilities Required

#### 💻 Online

For online drives, the system should capture:

* Meeting Link
* Drive Date
* Time
* Individual Candidate Interview Time

---

# 📧 Candidate Communication

Once the placement drive is scheduled, students should automatically receive an email containing:

* Company Name
* Job Role
* Drive Date
* Reporting Time
* Drive Mode
* Venue / Meeting Link
* Other relevant instructions

The project should use standardized **correspondence templates** for official communication.

---

# 🎤 Interview Management

Interview panel members can access candidates who are waiting for an interview.

### Candidate Search

Panel members can search using:

* Student ID / Applicant ID

**OR**

* Job ID
* College Name

### Interview Queue

```text
Job ID + College
        ↓
List of Waiting Students
        ↓
Select Student
        ↓
View Student Details
        ↓
Conduct Interview
```

---

# 📝 Technical Interview Evaluation

The interview panel evaluates candidates based on multiple parameters.

### Evaluation Criteria

* Communication
* Technical Ability
* Project Explanation

The candidate receives a score **out of 50**.

The system then compares the candidate's performance against the configured cutoff.

### Candidate Decision

```text
Move Forward
      ↓
Next Stage
```

or

```text
On Hold
```

or

```text
Rejected
```

---

# 🎯 Technical Round

For the technical round, the current requirement specifies:

**Cutoff: Above 80**

Candidates who clear the required cutoff proceed to the next stage.

For example:

```text
Technical Evaluation
        ↓
Score > Cutoff
        ↓
Cleared
        ↓
HR Interview
```

Candidates who qualify should receive a **cleared notification email**.

---

# 👔 HR Interview

Candidates who successfully complete the technical round proceed to the HR interview.

### HR Flow

```text
Technical Round
      ↓
Qualified Candidates
      ↓
HR Interview
      ↓
Final Decision
      ↓
Selected / Rejected
```

Candidates who clear the HR interview receive a **selection/cleared email**.

---

# 👨‍🎓 Student Dashboard

Students should have access to a dashboard where they can track all their job applications.

### Applied Job Status

| Job ID | Company | Role     | Status   | Offer Acceptance |
| ------ | ------- | -------- | -------- | ---------------- |
| J1     | TCS     | Database | Selected | ☑                |

Possible statuses may include:

```text
Applied
Shortlisted
Interview Scheduled
Technical Round
HR Round
Selected
Rejected
On Hold
```

For selected candidates, an **Offer Acceptance** option should be available.

---

# 🔐 User Roles

The system consists of multiple user roles.

### 👨‍💼 Admin

Responsibilities:

* Approve/reject college registration
* Approve/reject company registration
* Manage registered organizations
* Monitor placement activities
* Manage system configurations

### 🏢 Company

Responsibilities:

* Register company
* Login using approved credentials
* Post jobs
* View college requests
* Schedule interviews
* View candidate information
* Conduct/evaluate interviews
* Update candidate status

### 🏫 College

Responsibilities:

* Register college
* Login using approved credentials
* Manage student information
* View available jobs
* Apply for jobs
* Upload eligible student data through Excel
* Track student placement status

### 👨‍🎓 Student

Responsibilities:

* Register
* Complete personal and academic information
* Upload resume and documents
* Apply for jobs through the college
* View application status
* View interview information
* Accept/reject offer where applicable

### 👥 Interview Panel

Responsibilities:

* View scheduled candidates
* Search candidates
* View student details
* Evaluate candidates
* Enter marks
* Provide suggestions
* Move candidates to the next stage
* Put candidates on hold
* Reject candidates

---

# 📩 Email & Correspondence

The system should support standardized email communication for important recruitment events.

Examples:

* Registration Confirmation
* Registration Approval
* Registration Rejection
* Job Application
* Interview Schedule
* Technical Round Cleared
* HR Interview
* Final Selection
* Rejection
* Offer Acceptance

Email templates should be configurable and reusable.

---

# ✅ Validation Requirements

The system should include appropriate validations for important fields.

### College

* College Name
* College Code
* Official Email
* Affiliation
* Location
* Required accreditation information

### Company

* Company Name
* CIN Number
* Official Email
* Sector
* Domain
* Location

### Security Validation

Possible validation mechanisms include:

* OTP verification
* Email verification
* Official email validation
* Required-field validation
* Format validation
* Duplicate registration checks

**Note:** CIN number should be entered manually and **must not use autocomplete**.

---

# 🛠️ UI/UX Considerations

The application should provide a simple and understandable interface.

Recommended improvements based on review feedback:

* Autocomplete where appropriate
* Dropdown/picklist for predefined values
* Tooltips for unfamiliar fields
* Clear multi-step registration
* Validation messages
* Status indicators
* Confirmation messages
* Responsive dashboards
* Clear navigation between recruitment stages

---

# 🔄 Overall Recruitment Workflow

```text
                 ┌───────────────┐
                 │     ADMIN     │
                 └───────┬───────┘
                         │
             Approve Companies/Colleges
                         │
          ┌──────────────┴──────────────┐
          ↓                             ↓
   ┌──────────────┐              ┌──────────────┐
   │   COMPANY    │              │   COLLEGE    │
   └──────┬───────┘              └──────┬───────┘
          │                             │
       Post Job                     View Job
          │                             │
          └─────────────┬───────────────┘
                        ↓
                 Job Application
                        ↓
              Upload Eligible Students
                        ↓
                Schedule Interview
                        ↓
               Student Notification
                        ↓
                Technical Interview
                        ↓
                 Evaluation / Cutoff
                   ↙    ↓      ↘
              Reject  Hold   Next Stage
                              ↓
                         HR Interview
                              ↓
                    ┌─────────┴─────────┐
                    ↓                   ↓
                 Selected            Rejected
                    ↓
              Offer Acceptance
```

---

# 📅 Project Milestones

| Milestone       | Module                                  | Review Date |
| --------------- | --------------------------------------- | ----------- |
| MLP01           | College & Company Registration          | 27 Dec      |
| MLP02           | Job Request & Recruitment               | 30 Dec      |
| Review          | Registration & Validation Improvements  | 29 Dec      |
| Review          | Recruitment Flow & Interview Management | 5 Jan       |
| Next Connection | Project Progress Review                 | 2 Jan       |

---

# 📝 Review Feedback Incorporated

The following requirements were identified during project reviews:

* College name autocomplete to be evaluated.
* College code format validation to be considered.
* Affiliation should use an appropriate picklist.
* Location selection should be standardized.
* Tooltips should be added where necessary.
* Official email IDs should be used.
* Email correspondence templates should be created.
* Company name autocomplete to be evaluated.
* CIN format validation should be implemented.
* CIN must **not** use autocomplete.
* Sector, domain, and location should use standardized selections where applicable.
* OTP validation should be considered.
* Rejected registrations must remain stored with a rejection status.
* Campus Recruitment module should be renamed appropriately.
* Placement Drive Schedule should clearly display the requested job.
* Eligible students should be uploaded after selecting a job.
* Excel-to-database import needs to be implemented.
* Interview scheduling must display college and student information.
* Offline and online drive modes must be supported.
* Candidate-specific online interview timings should be supported.
* Interview evaluation should include communication, technical ability, and project explanation.
* Technical cutoff should be configurable.
* Students should receive automated email notifications.
* Students should be able to track application status.

---

# 🚀 Future Enhancements

Possible future improvements include:

* Automated eligibility checking
* Resume parsing using AI
* AI-based candidate shortlisting
* Interview analytics
* Placement statistics dashboard
* Company-wise recruitment analytics
* College-wise placement analytics
* Automated interview scheduling
* Email/SMS notification integration
* Offer letter generation
* Digital offer acceptance
* Advanced reporting and analytics
* Role-based access control
* Audit logs
* Bulk student data import with validation

---

# 📌 Project Status

**Current Status:** 🚧 Under Development

The project is being developed incrementally through multiple milestones, beginning with registration and progressing toward complete placement drive and recruitment management.

---

## 📂 Repository

**Project Name:** `UAP_Project21_PlacementDriveManagement-R`

**Team:** Lads
**Team Lead:** Abdul Sathar
**Scrum Master:** Dharunesh

---

## 🎓 Academic Project

This project is developed as part of the **UAP / Placement Drive Management** project initiative and focuses on applying software development, database management, workflow automation, and recruitment management concepts to a real-world placement scenario.
