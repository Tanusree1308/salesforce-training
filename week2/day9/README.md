# Day 9 - LWC Communication & Data Flow

## Introduction

Today I learned how Lightning Web Components communicate with each other, how data flows through Salesforce applications, and why modular architecture is important for enterprise systems.

---

# Component Communication

## Why Components Communicate

In modern applications, components rarely work independently. They need to exchange information to keep the user interface synchronized and responsive.

### Examples

- Student Form sends data to Student Dashboard
- Attendance Component updates Attendance Summary
- Notification Component displays system alerts
- Course Component updates enrollment status

Component communication helps applications remain dynamic and interactive.

---

# Dashboard Architecture

## Student Dashboard

### Components

- Header Component
- Student Profile Component
- Attendance Component
- Course Component
- Notification Component

### Communication Flow

```text
Student Profile
       ↓
Attendance Component
       ↓
Notification Component
```

When attendance changes, the Notification Component can display alerts regarding low attendance.

---

## Faculty Dashboard

### Components

- Header Component
- Faculty Profile Component
- Course Management Component
- Attendance Management Component
- Student Records Component

### Communication Flow

```text
Course Management
        ↓
Attendance Management
        ↓
Student Records
```

Faculty actions update student records and attendance information.

---

## Admin Dashboard

### Components

- Header Component
- User Management Component
- Course Management Component
- Reports Component
- Notification Component

### Communication Flow

```text
User Management
       ↓
Reports Component
       ↓
Notification Component
```

Administrative updates automatically reflect in reports and notifications.

---

# Parent-Child Communication

## Parent Component

A parent component contains one or more child components and passes data to them.

### Example

**Student Dashboard (Parent)**

- Student Profile (Child)
- Attendance Component (Child)
- Notification Component (Child)

Parent components send data to child components using properties.

---

## Child-to-Parent Communication

Child components communicate with parents using custom events.

### Example

```text
Attendance Component
        ↓ Event
Student Dashboard
```

When attendance is updated, the Attendance Component sends an event to the Student Dashboard.

---

# Data Flow Thinking

## Selected Process: Student Registration

### Complete Flow

```text
UI
 ↓
Validation
 ↓
Flow
 ↓
Apex
 ↓
Database
 ↓
Notification
```

### Step 1: UI

The student enters:

- Name
- Roll Number
- Department
- Email

and clicks the **Register** button.

### Step 2: Validation

The system checks:

- Required fields
- Valid email format
- Duplicate registration

If validation fails, an error message is displayed.

### Step 3: Flow

The registration request is sent to Salesforce Flow or the appropriate business process.

### Step 4: Apex

Apex executes business logic such as:

- Creating student records
- Verifying constraints
- Processing registration rules

### Step 5: Database

The validated information is stored in Salesforce objects.

### Step 6: Notification

The system displays:

> Student Registration Successful

or sends an email notification.

---

# Aura vs LWC

## Aura Components

Aura was Salesforce's earlier component framework.

### Advantages

- Enabled component-based development
- Supported dynamic applications

### Limitations

- Slower performance
- Complex framework
- More boilerplate code
- Less aligned with web standards

---

## Lightning Web Components (LWC)

LWC is Salesforce's modern framework built using standard web technologies.

### Advantages

- Faster rendering
- Better performance
- Modern JavaScript support
- Easier maintenance
- Reduced complexity
- Better scalability

---

# Why Salesforce Moved from Visualforce/Aura to LWC

Salesforce adopted LWC because:

- Improved performance
- Better user experience
- Modern web standards
- Faster development
- Easier maintenance
- Better scalability
- Reduced framework overhead

LWC allows developers to build enterprise-grade applications using modern development practices.

---

# Visualforce Overview

Visualforce is Salesforce's legacy UI technology.

### Purpose

- Build custom Salesforce pages
- Create user interfaces before Aura and LWC existed

### Current Status

Visualforce is still supported but is mainly used for maintaining older applications.

New Salesforce projects generally prefer Lightning Web Components.

---

# Reflection

## Why do Enterprise Applications Need Modular Architecture?

Enterprise systems are large and continuously evolving.

### Benefits

- Reusability
- Scalability
- Easier maintenance
- Better testing
- Faster development
- Team collaboration
- Reduced complexity

By breaking applications into smaller independent modules, developers can update one part of the system without affecting the entire application.

---

# Revision Questions

## 1. Why do components communicate?

Components communicate to share data, update information, and keep the user interface synchronized.

## 2. Difference between parent-child communication and events?

Parent-to-child communication passes data using properties.

Child-to-parent communication uses events to notify the parent component about changes.

## 3. Why is modular architecture useful?

It improves maintainability, scalability, reusability, and testing.

## 4. Why did Salesforce move toward LWC?

To improve performance, support modern web standards, and simplify development.

## 5. What problems happen in tightly coupled systems?

- Difficult maintenance
- Poor scalability
- Higher development costs
- Increased bugs
- Complex updates

## 6. Why is frontend architecture important?

Good frontend architecture improves user experience, maintainability, and performance.

## 7. Why should UI and backend remain separate?

Separation improves security, scalability, maintainability, and code organization.

## 8. Why do large systems need reusable modules?

Reusable modules reduce duplication, speed up development, and simplify maintenance.

---

# Day 9 Outcome

After completing Day 9, I learned:

- Component communication
- Parent-child interaction
- Event-driven architecture
- Data flow in Salesforce applications
- Dashboard design principles
- Aura vs LWC differences
- Modular enterprise architecture
