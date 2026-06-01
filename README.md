# 📦 Courier Management System (CMS) — Salesforce

> A cloud-based courier and logistics management system built entirely on the Salesforce platform, automating shipment tracking, delivery assignments, billing, and performance analytics.

---

## 🚀 Project Overview

Manual courier operations lead to delayed updates, scheduling conflicts, and poor customer visibility. This project replaces those fragmented processes with a **centralized Salesforce solution** that manages the full shipment lifecycle — from booking to invoice — in a single platform.

Built as a final-year BCA academic project (Team Lead: Gunasekar B), this system demonstrates real-world Salesforce administration skills including data modeling, automation flows, role-based security, and dashboard reporting.

---

## ✨ Key Features

| Feature | Description |
|---|---|
| 📋 Shipment Booking | Create and manage parcels with auto-generated tracking numbers (SHP-00001) |
| 🚚 Real-time Status Tracking | Automated flow updates shipment status whenever a Delivery Update is logged |
| 👤 Agent Assignment | Link delivery agents to shipments with branch-level management |
| 🧾 Invoice Generation | Auto-numbered invoices (INV-0001) tied to delivered shipments |
| 📊 Reports & Dashboards | Shipment Status Summary, Agent Performance, and Revenue by Branch reports |
| 🔐 Role-Based Access Control | 4 custom profiles: Courier Admin, Branch Manager, Delivery Agent, Customer Support |
| ✅ Validation Rules | 10+ rules enforcing data quality (email format, phone digits, weight > 0, etc.) |

---

## 🗂️ Data Model

```
Customer__c ──► Shipment__c ──► Delivery_Update__c (Master-Detail)
                     │
                     ├──► Delivery_Agent__c ──► Branch__c
                     │
                     └──► Invoice__c
```

**Custom Objects:**
- `Customer__c` — stores personal and contact info
- `Shipment__c` — manages parcel details with auto-number tracking
- `Delivery_Agent__c` — agent profiles linked to branches
- `Branch__c` — courier branch offices
- `Delivery_Update__c` — status logs per shipment (Master-Detail)
- `Invoice__c` — billing records per delivery

---

## ⚙️ Technology Stack

| Layer | Technology |
|---|---|
| UI | Salesforce Lightning Experience |
| Database | Salesforce Custom Objects |
| Automation | Record-Triggered Flows |
| Validation | Salesforce Validation Rules |
| Security | Profiles, Roles, Sharing Rules |
| Reporting | Reports & Dashboards |

---

## 🔄 Process Flow

```
Customer Input → Shipment Creation → Validation → Agent Assignment
       → Transit → Delivery Update → Invoice → Reports
```

---

## 🔐 Security Model

**Role Hierarchy:**
```
Courier Admin
    └── Branch Manager
            ├── Delivery Agent
            └── Customer Support
```

**Profile Permissions:**

| Profile | Customer | Shipment | Delivery Update | Invoice |
|---|---|---|---|---|
| Courier Admin | Full CRUD | Full CRUD | Full CRUD | Full CRUD |
| Branch Manager | Create/Read/Edit | Create/Read/Edit | Create/Read/Edit | Read |
| Delivery Agent | Read | Read/Edit | Create/Read/Edit | Read |
| Customer Support | Read/Edit | Read/Edit | Read | Read |

---

## 📈 Reports & Dashboards

Three reports built as custom Report Types:

1. **Shipment Status Summary** — grouped by status, summarized by revenue (donut chart)
2. **Agent Performance Report** — shipments per agent, avg delivery time (bar chart)
3. **Revenue by Branch Report** — monthly revenue breakdown per branch (column chart)

All three feed into the **Courier Management Dashboard** shared with Courier Admin, Branch Managers, and Customer Support.

---

## 🧪 Automation Highlight

**Auto-Update Shipment Status Flow:**
> Trigger: `Delivery_Update__c` record created
> Action: Updates linked `Shipment__c.Status__c` with the new delivery status
> Result: Zero manual status updates needed across the delivery lifecycle

---

## 📅 Project Timeline (Agile Sprints)

| Sprint | Epic | Story Points |
|---|---|---|
| Sprint 1 | Developer Setup | 3 |
| Sprint 2 | Data Modeling | 5 + 5 |
| Sprint 3 | Automation + Validation | 3 + 3 |
| Sprint 4 | Security (Profiles & Roles) | 5 |
| Sprint 5 | Reports | 4 |
| Sprint 6 | Dashboards | 4 |

---

## 👥 Team

| Name | Role | Reg. No |
|---|---|---|
| Gunasekar B | Team Lead | 32723U09035 |
| Hariprasath P | Member | 32723U09036 |
| Hari Haran R | Member | 32723U09037 |
| Imthyaz S | Member | 32723U09038 |
| Jeevanatham R | Member | 32723U09039 |

---

## 🛠️ How to Explore This Project

1. Sign up for a free [Salesforce Developer Org](https://developer.salesforce.com/signup)
2. Follow the milestone steps in the project documentation
3. Create custom objects, fields, and relationships as described
4. Build the Record-Triggered Flow for auto status updates
5. Set up profiles, roles, and users
6. Create reports and the Courier Management Dashboard

> 💡 No code required — this project is built entirely through Salesforce's point-and-click admin tools.

---

## 📚 What I Learned

- Designing normalized data models with Lookup and Master-Detail relationships
- Writing formula-based validation rules for data integrity
- Building record-triggered automation flows without Apex code
- Implementing role-based security with profiles and sharing rules
- Creating summary reports and visual dashboards for business insights
- Agile sprint planning with story points and velocity tracking

---

## 🔮 Future Scope

- Mobile tracking app with GPS integration
- SMS/email notifications via Salesforce Flow
- AI-based delivery route optimization (Einstein)
- Multi-branch analytics with territory management

---

*Academic project — BCA Final Year | Salesforce Developer Org*
