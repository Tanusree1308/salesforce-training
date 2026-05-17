# Campus Connect – Salesforce Concepts & Workflow

## 1. Why Testing Matters
In enterprise systems, writing code is only one part of development; ensuring the code works reliably is equally important. Testing helps prevent critical bugs from reaching production and ensures that existing functionality does not break when new features are added.

Instead of relying on assumptions, Apex Test Classes validate that triggers, classes, and automations behave correctly for both normal scenarios and unexpected edge cases. Proper testing improves system stability, reliability, and user trust.

---

## 2. What is Asynchronous Apex?
Asynchronous Apex allows processes to run in the background instead of making users wait for completion during screen interactions (synchronous processing).

It is mainly used for resource-intensive operations such as:
- Sending bulk student notifications
- Integrating with external finance systems
- Generating large academic reports

Running these tasks asynchronously improves system performance and helps avoid Salesforce governor limit issues.

---

## 3. What is Salesforce DX?
Salesforce DX (Developer Experience) is a modern development approach that shifts Salesforce development from an **org-centric** model to a **source-driven** workflow.

Using tools like:
- Salesforce CLI
- VS Code
- GitHub
- Scratch Orgs

Developers can:
- Write code locally
- Track changes efficiently
- Collaborate with teams easily
- Test features in temporary environments
- Deploy applications more safely

This modern workflow improves productivity and code management in enterprise projects.

---

# 4. Complete System Workflow (Campus Connect)

## Step 1: Student Registration
A student registers for a new course such as **"Introduction to Computer Science"** through the university portal.

## Step 2: Validation Rules
Before saving the record, Salesforce validates:
- Email format
- Required fields
- Course prerequisites

## Step 3: Trigger Execution
An Apex **Before Insert Trigger** checks the course capacity.

- If the course is full → Enrollment is blocked
- If seats are available → Seat count is updated automatically

## Step 4: Formula Field Calculation
A formula field recalculates the student's total semester credits instantly after enrollment.

## Step 5: Platform Event Publishing
A Platform Event is triggered in the background to notify the university finance system for invoice generation.

## Step 6: Database Commit
The `Enrollment__c` record is securely stored in the Salesforce database.

## Step 7: Flow Automation
A Record-Triggered Flow automatically sends a course registration confirmation email to the student.

## Step 8: Reports & Dashboards
Administrative reports and dashboards update in real time to reflect the latest enrollment statistics.

---

# 5. Important Test Cases

## 1. Invalid Email Entry
### Test:
Attempt to register a student using an invalid email such as:
```txt
john.smith@
```

### Risk if Not Tested:
Email automation may fail and cause the transaction to roll back.

---

## 2. Duplicate Registration
### Test:
Attempt to enroll the same student into the same course twice.

### Risk if Not Tested:
- Duplicate billing
- Incorrect enrollment counts
- Data inconsistency

---

## 3. Course Overbooking
### Test:
Attempt to enroll a 31st student into a course with a maximum capacity of 30 students.

### Risk if Not Tested:
- Overcrowded classrooms
- Incorrect seat allocation
- Resource management issues

---

## 4. Waitlist Trigger Logic
### Test:
Remove an enrolled student from a full class and verify that the first waitlisted student is automatically enrolled.

### Risk if Not Tested:
Available seats may remain empty due to automation failure.

---

## 5. Attendance Percentage Validation
### Test:
Enter invalid attendance values such as:
```txt
110%
-5%
```

### Risk if Not Tested:
Incorrect attendance records may affect academic evaluations and reports.

---

# 6. Reflection: Importance of Structured Workflows

For small projects, directly configuring features in Salesforce may be manageable. However, enterprise-level software development requires structured workflows to support teamwork, maintain system stability, and avoid deployment issues.

Professional developers use:
- Salesforce CLI
- Salesforce DX
- GitHub
- Version Control Systems

These tools help teams:
- Track every code change
- Identify who modified the code
- Prevent accidental overwrites
- Deploy updates safely
- Maintain reliable production systems

Without structured workflows, organizations risk:
- Code conflicts
- Broken deployments
- System outages
- Reduced productivity

A source-driven development approach improves collaboration, reliability, and long-term maintainability of enterprise applications.

---
