# **Day 5: Introduction to Apex**

## **1. What is Apex?**

Apex is Salesforce’s object-oriented programming language that allows developers to add custom business logic to applications on the Salesforce Platform. It is similar to Java and is designed specifically for cloud-based application development.

Apex is mainly used for:
- Writing custom business logic
- Creating triggers
- Automating backend processes
- Handling complex validations
- Integrating external systems

---

# **2. Features of Apex**

Some important features of Apex include:

- Strongly typed language
- Object-oriented programming support
- Built-in database operations
- Easy integration with Salesforce objects
- Support for triggers and asynchronous processing

Apex runs directly on Salesforce servers, making it secure and scalable for enterprise applications.

---

# **3. Apex Syntax Basics**

An Apex class contains variables, methods, and logic similar to other programming languages.

### **Basic Apex Program**

```apex
public class StudentGreeting {

    public static void displayMessage() {
        String studentName = 'Tanusree';

        System.debug('Welcome to Salesforce Apex, ' + studentName);
    }
}
```

### **Explanation**
- `public class` defines a new Apex class.
- `displayMessage()` is a method inside the class.
- `String` stores text data.
- `System.debug()` prints output in the debug logs.

---

# **4. Working with Variables and Conditions**

Apex supports variables, conditional statements, and loops for implementing business logic.

### **Example: Checking Student Eligibility**

```apex
public class StudentEligibility {

    public static void checkEligibility() {

        Decimal cgpa = 3.8;

        if(cgpa >= 3.5) {
            System.debug('Eligible for Scholarship');
        }
        else {
            System.debug('Not Eligible');
        }
    }
}
```

### **Explanation**
- `Decimal` is used for numeric values containing decimals.
- The `if-else` statement checks the CGPA condition.
- Depending on the condition, Salesforce prints the corresponding message.

---

# **5. SOQL in Apex**

SOQL (Salesforce Object Query Language) is used in Apex to retrieve records from Salesforce objects.

### **Example: Fetching Student Records**

```apex
List<Contact> studentList = [
    SELECT Id, Name, Email
    FROM Contact
    LIMIT 5
];

System.debug(studentList);
```

### **Explanation**
- `SELECT` retrieves fields from the object.
- `FROM Contact` specifies the Salesforce object.
- `LIMIT 5` restricts the number of returned records.

---

# **6. Apex Use Cases**

Apex is commonly used in Salesforce projects for:
- Trigger automation
- Data validation
- Record processing
- Integration logic
- Batch processing
- Scheduled jobs

It helps developers build scalable and customized enterprise applications.

---

# **7. Reflection: Importance of Apex**

While Salesforce provides many low-code tools, some business requirements need advanced customization. Apex allows developers to implement complex logic that cannot be achieved using only clicks and configuration.

By combining Apex with Salesforce automation tools, developers can create efficient, scalable, and secure cloud applications.

##**8. Sample Code**
## **Simple Apex Program**

```apex
public class HelloWorld {

    public static void showMessage() {

        System.debug('Hello Salesforce!');
    }
}
```

### **Explanation**
- `public class HelloWorld` creates a new Apex class.
- `showMessage()` is a method inside the class.
- `System.debug()` prints the message in the debug log.
- This is one of the simplest examples used to understand Apex syntax and structure.
