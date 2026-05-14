# **Day 6: Triggers & SOQL**

## **1. What is SOQL?**

SOQL (Salesforce Object Query Language) is used in Salesforce to retrieve data from objects. It works similarly to SQL, but it is specially designed for Salesforce databases and records.

Using SOQL, we can:
- Fetch records from objects
- Apply conditions to filter data
- Access related object information
- Sort records
- Limit the number of results returned

### **Basic SOQL Example**

```apex
SELECT Name, Email
FROM Contact
WHERE Department__c = 'CSE'
```

This query retrieves students who belong to the CSE department.

---

# **2. What is an Apex Trigger?**

An Apex Trigger is a piece of code that runs automatically whenever changes happen to Salesforce records.

Triggers can execute when records are:
- Created
- Updated
- Deleted
- Restored

They are commonly used to automate backend tasks such as:
- Sending notifications
- Validating data
- Updating related records
- Applying business logic automatically

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

This trigger automatically assigns the department as **"General"** if the field is left empty while creating a student record.

---

# **3. Difference Between Flow and Trigger**

| Flow | Apex Trigger |
|---|---|
| Uses a drag-and-drop interface | Uses Apex programming |
| Easier for beginners and admins | Requires coding knowledge |
| Best for simple automation | Better for complex business logic |
| Faster to configure | More flexible and customizable |
| Mostly low-code | Fully code-based |

## **Flow vs Trigger Thinking**

| Scenario | Best Choice | Reason |
|---|---|---|
| Sending a simple welcome email | Flow | Easy to build without writing code |
| Complex fee eligibility calculation | Apex Trigger | Requires advanced conditions and logic |
| Updating related records automatically | Trigger | Handles relationships more efficiently |
| Calling an external API | Trigger | Provides better control for integrations |
| Student approval workflow | Flow | Easy to visualize and maintain |

---

# **4. Difference Between Before and After Trigger**

| Before Trigger | After Trigger |
|---|---|
| Runs before saving records | Runs after records are saved |
| Used for validation and field updates | Used for notifications and related actions |
| Records can still be modified | Records become read-only |
| Faster for updating field values | Better for post-save operations |

### **Examples**
- **Before Trigger:** Validate CGPA before saving the student record.
- **After Trigger:** Send a confirmation email after registration.

---

# **5. Your Trigger Use Cases**

## **1. Welcome Email After Registration**
Whenever a new student registers, the system automatically sends a welcome email.

### **Trigger Event**
After Insert

---

## **2. Course Full Notification**
If a course reaches maximum capacity, the assigned faculty member gets notified automatically.

### **Trigger Event**
After Update

---

## **3. Attendance Warning**
If a student's attendance drops below 75%, the system generates a warning message.

### **Trigger Event**
After Update

---

## **4. Scholarship Eligibility Update**
Students with a CGPA above 3.5 are automatically marked as scholarship eligible.

### **Trigger Event**
After Update

---

## **5. Faculty Assignment Notification**
When a professor gets assigned to a course, the department receives an automatic notification.

### **Trigger Event**
After Insert / After Update

---

# **6. Query Examples (English Query Ideas)**

## **Student Queries**
- Find all students enrolled in Course A.
- Find students whose attendance is below 75%.
- Find students eligible for scholarships.
- Display students from the CSE department.

---

## **Course Queries**
- Find all available courses.
- Find courses that are already full.
- Display courses handled by Professor Ravi.

---

## **Faculty Queries**
- Find all courses assigned to Faculty X.
- Display professors from the Computer Science department.
- Find faculty members handling multiple courses.

---

# **7. Reflection: Why Enterprise Systems Need Event-Driven Behavior**

Enterprise systems handle a huge amount of data every day. In large organizations, manually checking every record update or sending notifications individually is not practical.

Event-driven behavior allows the system to react automatically whenever data changes happen.

For example:
- Sending automatic emails
- Updating related records instantly
- Validating important information
- Generating warnings automatically
- Triggering approval processes

This automation helps organizations:
- Save time
- Reduce manual work
- Improve accuracy
- Maintain consistent data
- Increase overall efficiency

Technologies like Salesforce Flows and Apex Triggers make enterprise systems smarter by allowing them to respond automatically to real-time changes in data.
