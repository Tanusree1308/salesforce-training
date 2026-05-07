# Day 1: Salesforce CRM Basics

## 1. What is CRM?
**CRM (Customer Relationship Management)** is a centralized platform used to manage all company-customer interactions. It replaces fragmented tools like spreadsheets and personal inboxes with a single **"Customer 360"** view, ensuring every department sees the same real-time data.

* **The Goal:** To reduce technical complexity, lower IT costs (by up to 25%), and increase employee productivity.
* **The Impact:** 89% of customers see a positive ROI within their first year.

![Customer 360 Ecosystem](pic1.png)

---

## 2. Platform Interface & Navigation
The Lightning Experience interface is designed for high productivity and quick access to data:

* **Home:** A customizable dashboard showing daily tasks, performance charts, and recent records.
* **Global Search:** Accessible via the forward slash (`/`) hotkey to find any record instantly.
* **App Launcher:** The "Waffle Icon" used to switch between apps like Sales, Service, or Marketing.
* **Setup:** The "Cog Wheel" area used for backend configurations and user management.

---

## 3. Core Objects (The Building Blocks)
Salesforce data is structured into **Objects**, which represent real-world business entities:

* **Leads:** Unqualified potential customers (the "dumping ground" for new inquiries).
* **Accounts:** The companies or organizations you do business with.
* **Contacts:** The individual people associated with those Accounts.
* **Opportunities:** Qualified business deals currently in progress.
* **Products:** The specific goods or services offered to customers.

---

## 4. The Sales Lifecycle: Lead to Opportunity
A core function of the CRM is moving interest through a defined pipeline.

1. **Nurturing:** Tracking interactions with a Lead to see if they meet business criteria (Budget, Authority, Need, and Timing).
2. **Conversion:** Once qualified, a Lead is "Converted." This action automatically creates three linked records: an **Account**, a **Contact**, and an **Opportunity**.

![Lead Conversion Success](pic2.png)


---

## 5. Automation & Pipeline Management
* **Kanban View:** A visual board to track deal progression through stages. It allows users to drag-and-drop deals to update their status instantly.
* **Flow Builder:** An automation tool used to create workflows (e.g., sending an automatic email when a Lead is created) without writing code.
* **Dashboards:** Visual charts and graphs that help leaders make data-driven decisions based on real-time reports.

---

## 6. Technical Configuration
For developers and admins, the backend of the system is managed through the **Object Manager**. This is where you define the data architecture, create custom fields, and manage how data relates across the entire organization.

![Object Manager View](pic3.png)
