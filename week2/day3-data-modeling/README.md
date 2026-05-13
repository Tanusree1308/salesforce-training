# **Day 3: Data Modeling**

## **1. App vs. Object vs. Record vs. Field**

To better understand Salesforce data organization, we can compare it to a digital storage system used in everyday work environments.

- **App:** Think of an App as a complete workspace or filing cabinet. It contains related tools, tabs, and objects built for a particular process or team. For example, a **"Campus Connect"** app can be created for managing college admissions.

- **Object:** An Object acts like a folder inside the cabinet or a table inside a database. Each object stores a specific category of information such as Students or Courses.

- **Record:** A Record represents one individual entry stored inside an object. For instance, a single student profile for **"Thafil"** is considered a record.

- **Field:** Fields are the individual attributes that store details about a record. Examples include First Name, Email, Department, and GPA.

---

# **2. Standard vs. Custom Objects**

## **Standard Objects**
Standard Objects are the built-in objects provided by Salesforce for handling common CRM operations.

Examples:
- Account
- Contact
- Lead
- Opportunity

These objects already contain predefined functionality and relationships.

### **Working with Standard Objects**
![Contact Object Details](Screenshot%202026-05-09%20170442.png)

---

## **Custom Objects**
Custom Objects are created to support business requirements specific to an organization.

In a college management system, objects such as:
- Professor__c
- Course__c
- Enrollment__c

are examples of custom objects. The `__c` suffix indicates that the object is custom-built.

---

# **3. Your College Data Model**

This data model demonstrates how students, professors, departments, and courses are connected within the system.

## **Objects & Relationships**

### **Department to Professor**
A Lookup Relationship is used because one department can contain multiple professors.

### **Professor to Course**
A Lookup Relationship connects professors with the courses they teach.

### **Student to Course**
A Many-to-Many Relationship is implemented using **Enrollment__c** as a Junction Object.  
This object contains Master-Detail relationships with both Student and Course objects.

---

## **Data Model Diagrams**

### **Conceptual Data Model Diagram**
![Conceptual Data Model](YOUR-FIRST-IMAGE.png)

### **Salesforce Schema Builder Execution**
![Salesforce Schema Builder Screenshot](YOUR-SECOND-IMAGE.png)

---

# **4. Formula Fields**

## **Explanation**
Formula Fields are automatically calculated fields whose values depend on other fields or expressions. Since they update dynamically, users do not need to manually edit them.

### **Example 1: Full_Name__c (Text)**
Instead of entering the full name manually, this formula combines the first and last name fields.

Formula:

```text
First_Name__c & " " & Last_Name__c
```

### **Example 2: Honor_Roll_Eligible__c (Checkbox)**
This formula automatically determines whether a student qualifies for the honor roll based on CGPA.

Formula:

```text
CGPA__c >= 3.5
```

---

# **5. Validation Rules**

## **Explanation**
Validation Rules ensure that users enter valid and meaningful data before saving records. If the rule condition becomes true, Salesforce blocks the save operation and displays an error message.

---

## **Example 1: Prevent_Future_DOB**

This validation rule prevents users from entering a future date for a student's birth date.

### **Error Condition**

```text
Date_of_Birth__c > TODAY()
```

### **Error Message**

```text
"A student's Date of Birth cannot be in the future."
```

---

## **Example 2: Valid_GPA_Range**

This rule checks whether the entered CGPA falls within an acceptable range.

### **Error Condition**

```text
CGPA__c < 0.0 || CGPA__c > 4.0
```

### **Error Message**

```text
"Please enter a valid CGPA between 0.0 and 4.0."
```

---

# **6. Reflection: Why Structured Enterprise Data Matters**

Structured data plays a major role in maintaining consistency and reliability across enterprise systems. Without a proper data model, users may enter inconsistent values like "Computer Science", "CS", or "Comp Sci", which can create confusion in reporting and automation.

By implementing objects, relationships, formula fields, and validation rules, organizations can maintain a reliable **Single Source of Truth**.

A structured system helps:
- Improve data accuracy
- Reduce duplicate records
- Simplify reporting
- Support automation
- Enable efficient collaboration between departments

Most importantly, reliable data allows organizations to confidently automate processes and make better business decisions.

### **Final System Verification**
![Org Authentication Success](Screenshot%202026-05-09%20194147.png)
