# EventForce Management System

## 📌 Project Overview

**EventForce Management System** is a Salesforce-based CRM solution designed to streamline and manage event planning operations.

The system provides a centralized platform for managing **clients, events, venues, vendors, and feedback**, while reducing manual work through Salesforce automation, approval processes, Apex logic, security controls, reports, and dashboards.

This project was developed as a **collaborative team project** using Salesforce configuration and development features.

---

## 👥 Team Members

| Name | Role |
|------|------|
| **Athulya A.** | Team Leader |
| **Janani A.** | Team Member |
| **Pooja S.** | Team Member |
| **Samyuktha K.** | Team Member |

---

## 🎯 Objectives

The main objectives of the EventForce Management System are to:

- Manage client information and event bookings.
- Maintain venue details and availability.
- Manage vendors and their service information.
- Prevent duplicate venue bookings.
- Automate client reminders before events.
- Handle event cancellation requests through an approval process.
- Manage user access based on roles and responsibilities.
- Provide reports and dashboards for event monitoring.
- Maintain data accuracy through validation rules and automation.

---

## 🛠️ Technologies & Salesforce Features

- Salesforce CRM
- Lightning App
- Custom Objects
- Custom Fields
- Object Relationships
- Validation Rules
- Record-Triggered Flows
- Scheduled Paths
- Approval Processes
- Apex Classes
- Apex Triggers
- Profiles
- Roles
- Permission Sets
- Organization-Wide Defaults
- Sharing Rules
- Reports
- Dashboards
- Data Import Wizard

---

## 📦 Main Modules

### 1. Event Management

The Event module manages event-related information such as:

- Event Name
- Event Date
- Event Type
- Event Status
- Event Budget
- Client
- Venue

Supported event types include:

- Wedding
- Corporate
- Birthday
- Anniversary
- Festival
- Concert
- Other

### 2. Client Management

The Client module stores:

- Client Name
- Email
- Phone
- Address
- City
- Country

A validation rule is implemented to ensure valid email addresses are entered.

### 3. Venue Management

The Venue module manages:

- Venue Name
- Address
- Location
- Capacity
- Availability Status

Venue availability is updated based on event status.

### 4. Vendor Management

The Vendor module manages vendor information and services, including:

- Catering
- Decor
- Photography
- Videography
- Lighting
- Stage Setup
- Makeup Artist
- DJ/Music
- Transportation
- Hosting/Anchor

### 5. Feedback Management

The Feedback module allows feedback to be associated with events and clients.

It includes:

- Rating
- Comments
- Feedback record

Ratings are maintained on a scale of **1 to 5**.

---

## 🔗 Salesforce Data Model

The project contains the following custom objects:

- `Event__c`
- `Client__c`
- `Vendor__c`
- `Venue__c`
- `Feedback__c`
- `EventVendor__c`

### Relationships

- Event → Client
- Event → Venue
- Feedback → Event
- Feedback → Client
- EventVendor → Event
- EventVendor → Vendor

---

## ⚙️ Automation

### 3-Day Client Reminder Flow

A record-triggered flow named:

`Client Reminder - 3 Days Before`

is implemented on the Event object.

When an event is confirmed, the flow schedules an action **three days before the Event Date** and automatically sends an email reminder to the client.

The event owner is also included as a CC recipient.

### Event Cancellation Approval Process

The project includes:

`Event_Cancellation_Process`

When an event status is changed to **Pending Cancellation**, the record enters the approval process for manager review.

If approved:

**Event Status → Canceled**

If rejected:

**Event Status → Rejected**

---

## 💻 Apex Development

Apex is used to implement additional business logic.

### Venue Status Management

The `VenueStatusHelper` Apex class updates venue availability based on event status.

### Duplicate Booking Prevention

Apex trigger logic is implemented to prevent duplicate bookings for the same venue and event date.

### Event Status Automation

Batch/Schedulable Apex is used to update past events to the appropriate completed status.

---

## 🔐 Security Configuration

The system uses Salesforce security features to control access.

### Profiles

- Event Admin
- Event Coordinator
- Vendor Manager
- Client

### Roles

- Event Admin
- Event Coordinator
- Vendor Manager
- Client

### Permission Set

`Feedback Manager`

### Organization-Wide Default

**Private**

### Sharing Rule

`Event_Sharing_For_Vendors`

---

## 📊 Reports & Dashboards

### Report

**Upcoming Events by Month**

Provides a summary of upcoming events and their monthly distribution.

### Dashboard

**EventForce Operations Dashboard**

Provides a visual overview of event information for monitoring and analysis.

---

## 🧪 Validation & Testing

The project includes validation and testing for:

- Event creation
- Client records
- Venue availability
- Vendor records
- Event status changes
- Cancellation approval
- Automated reminders
- Duplicate booking prevention
- User access and security
- Reports and dashboards

Example validation message:

```text
Please Enter Valid Email Address.
