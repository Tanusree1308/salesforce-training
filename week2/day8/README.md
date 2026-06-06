# Day 8 - Lightning Web Components (LWC) Basics

## What is LWC?

Lightning Web Components (LWC) is Salesforce's modern framework for building user interfaces using standard web technologies such as HTML, JavaScript, and CSS.

Each Lightning Web Component consists of:

- HTML file (UI structure)
- JavaScript file (Business Logic)
- Metadata XML file (Configuration)

LWC follows a component-based architecture that allows developers to build reusable and efficient UI components.

---

## Why Salesforce Uses LWC

Salesforce uses Lightning Web Components because:

- Improved performance
- Faster rendering
- Modern web standards support
- Better developer experience
- Reusable components
- Easier maintenance
- Scalable enterprise applications

Compared to Aura Components, LWC is lightweight, faster, and more efficient.

---

# UI Thinking Exercise

## College Management System - Suggested UI Screens

### 1. Student Registration Form
Allows students to register and update their personal details.

### 2. Course Dashboard
Displays enrolled courses, available courses, and course information.

### 3. Attendance View
Shows attendance records and attendance percentages.

### 4. Faculty Panel
Allows faculty members to manage students, courses, and attendance.

### 5. Notifications Widget
Displays important announcements, exam schedules, and updates.

---

# Component Thinking

## Selected Screen: Student Dashboard

### Reusable Components

#### Header Component
- Application logo
- Navigation menu
- User profile section

#### Student Information Component
- Student Name
- Roll Number
- Department
- Semester

#### Attendance Component
- Attendance percentage
- Attendance history

#### Course Component
- Enrolled courses
- Course progress

#### Notification Component
- Announcements
- Alerts
- Upcoming events

### Why Reusable Components are Useful

- Reduces duplicate code
- Improves maintainability
- Faster development
- Consistent user experience
- Easier testing and debugging
- Better scalability

For example, the Notification Component can be reused across Student Dashboard, Faculty Panel, and Admin Dashboard.

---

# Frontend vs Backend Thinking

| Functionality | Frontend (UI) | Backend (Apex) |
|-------------|-------------|-------------|
| Button Click Handling | ✅ | ❌ |
| Display Data | ✅ | ❌ |
| Form Validation (Basic) | ✅ | ❌ |
| Notification Display | ✅ | ❌ |
| Database Operations | ❌ | ✅ |
| Fee Calculation | ❌ | ✅ |
| Business Rules | ❌ | ✅ |
| Access Control | ❌ | ✅ |
| Data Processing | ❌ | ✅ |

## Frontend Responsibilities

- Display forms
- Handle user interactions
- Show notifications
- Render dashboards
- Basic validation

## Backend Responsibilities

- Store and retrieve data
- Apply business rules
- Calculate fees
- Manage security
- Access databases
- Process records

---

# Secure Server-Side Development

Security is important because enterprise applications handle sensitive data.

## Key Security Concepts

- Authentication
- Authorization
- Access Control
- Data Protection
- Secure Coding Practices

## Common Risks

- Unauthorized access
- Data breaches
- Improper permissions
- Injection attacks

Developers should always enforce security rules on the server side and validate user input.

---

# Reflection

## Why do modern enterprise systems use component-based UI architecture?

Modern enterprise systems use component-based architecture because it improves scalability, maintainability, and development speed.

### Benefits

- Reusable UI components
- Better code organization
- Faster development
- Easier maintenance
- Consistent user experience
- Independent testing
- Team collaboration

Component-based design allows organizations to build large applications efficiently while maintaining quality and performance.

---

# Revision Questions

### 1. What is a component?
A component is a reusable and independent part of a user interface that performs a specific function.

### 2. Why are reusable components useful?
Reusable components reduce duplicate code, improve maintainability, and speed up development.

### 3. Difference between frontend and backend?
Frontend handles user interaction and UI, while backend manages business logic, security, and data storage.

### 4. Why did Salesforce move toward LWC?
Salesforce moved toward LWC to improve performance, adopt modern web standards, and enhance developer productivity.

### 5. Why is UI important in enterprise systems?
A good UI improves usability, productivity, and user satisfaction.

### 6. Why should systems separate UI and business logic?
Separation improves scalability, maintainability, security, and code organization.

### 7. What security risks exist in enterprise applications?
- Unauthorized access
- Data breaches
- Injection attacks
- Improper permissions

### 8. Why should developers think modularly?
Modular design improves reusability, testing, maintenance, and scalability.

---

# Day 8 Outcome

After completing Day 8, I learned:

- Lightning Web Components (LWC)
- Modern Salesforce UI architecture
- Component-based development
- Frontend and backend separation
- Reusable UI design principles
- Basic enterprise security concepts
