# **Day 6: Triggers & SOQL**

## **1. What is SOQL?**

SOQL (Salesforce Object Query Language) is a query language used to retrieve records from Salesforce objects. It is similar to SQL but is specifically designed for Salesforce data.

SOQL allows developers to:
- Fetch records from objects
- Filter data using conditions
- Retrieve related object data
- Sort and limit records
- Access Salesforce database information efficiently

### **Basic SOQL Example**

```apex
List<Contact> studentList = [
    SELECT Id, Name, Email
    FROM Contact
    WHERE Department__c = 'CSE'
    LIMIT 5
];

System.debug(studentList);
```

### **Explanation**
- `SELECT` specifies the fields to retrieve.
- `FROM Contact` defines the object.
- `WHERE` filters records based on conditions.
- `LIMIT` restricts the number of returned records.

SOQL is widely used in Apex classes, triggers, and controllers to work with Salesforce data. :contentReference[oaicite:0]{index=0}

---

# **2. What is an Apex Trigger?**

An Apex Trigger is a piece of Apex code that executes automatically before or after specific events occur on Salesforce records.

Triggers help automate backend operations whenever records are:
- Inserted
- Updated
- Deleted
- Undeleted

Triggers are commonly used for:
- Data validation
- Updating related records
- Sending notifications
- Implementing business logic
- Automating workflows

### **Simple Trigger Example**

```apex
trigger StudentTrigger on Contact (before insert) {

    for(Contact con : Trigger.new) {

        if(con.Department__c == null) {
            con.Department__c = 'General';
        }
    }
}
```

### **Explanation**
- The trigger runs before a Contact record is inserted.
- `Trigger.new` stores the incoming records.
- If the department field is empty, Salesforce automatically assigns "General".

Apex triggers execute automatically when database events occur on Salesforce objects. :contentReference[oaicite:1]{index=1}

---

# **3. Difference Between Flow and Trigger**

| Feature | Flow | Trigger |
|---|---|---|
| Development Type | Low-code / No-code | Code-based |
| Interface | Drag-and-drop UI | Apex programming |
| Complexity Handling | Suitable for simple automation | Better for complex logic |
| Performance | Good for standard automation | Better for heavy processing |
| Maintenance | Easier for admins | Requires developer knowledge |
| Flexibility | Limited customization | Highly customizable |

Flows are easier for administrators, while triggers provide greater flexibility for developers handling advanced business logic. :contentReference[oaicite:2]{index=2}

---

# **4. Difference Between Before and After Trigger**

| Before Trigger | After Trigger |
|---|---|
| Executes before data is saved | Executes after data is saved |
| Used for validation and updating fields | Used for related record operations |
| Records can be modified directly | Records become read-only |
| Faster for field updates | Useful for audit and logging operations |

### **Trigger Events**
- before insert
- before update
- before delete
- after insert
- after update
- after delete
- after undelete

Before triggers are generally used for validation and field updates, while after triggers are mainly used for actions involving related records. :contentReference[oaicite:3]{index=3}

---

# **5. Your Trigger Use Cases**

## **1. Automatic Department Assignment**
Automatically assign a default department when a new student record is created.

## **2. GPA Validation**
Prevent students from entering invalid CGPA values greater than 4.0.

## **3. Scholarship Eligibility**
Automatically mark students as scholarship eligible if their CGPA is above 3.5.

## **4. Course Enrollment Update**
Update course seat availability whenever a student enrolls in a course.

## **5. Attendance Warning Notification**
Generate a warning message if attendance falls below the minimum percentage.

Triggers help automate these processes instantly whenever data changes occur in the system.

---

# **6. Query Examples (English Query Ideas)**

## **Example 1**
Fetch all students belonging to the CSE department.

```apex
SELECT Name, Email FROM Contact
WHERE Department__c = 'CSE'
```

---

## **Example 2**
Retrieve students whose CGPA is greater than 3.5.

```apex
SELECT Name, CGPA__c FROM Contact
WHERE CGPA__c > 3.5
```

---

## **Example 3**
Display the latest enrolled students.

```apex
SELECT Name, CreatedDate FROM Contact
ORDER BY CreatedDate DESC
LIMIT 5
```

---

## **Example 4**
Fetch all available courses.

```apex
SELECT Name, Course_Code__c FROM Course__c
```

---

## **Example 5**
Retrieve students with attendance below 75%.

```apex
SELECT Name, Attendance__c FROM Contact
WHERE Attendance__c < 75
```

---

# **7. Reflection: Why Enterprise Systems React Automatically to Data Changes**

Modern enterprise systems handle massive amounts of data every second. Manual monitoring of every update is practically impossible. Automation tools such as Flows and Apex Triggers help systems react immediately whenever data changes occur.

For example:
- Sending notifications automatically
- Updating related records instantly
- Validating important information
- Preventing invalid data entry
- Maintaining data consistency across departments

Reactive systems improve:
- Accuracy
- Productivity
- Scalability
- User experience
- Operational efficiency

This is why enterprise platforms like Salesforce rely heavily on automation technologies such as Flow Builder, Apex, and Triggers to manage business operations effectively.

Salesforce automation tools are designed to react automatically to database events and business processes. :contentReference[oaicite:4]{index=4}
