# Customer Support Ticket Priority Prediction and Automated Assignment System

## Project Overview
This project aims to automate customer support ticket management in Salesforce using AI and automation. The system predicts ticket priority and auto-assigns it to the right agent, reducing manual effort and response time.

## Phase 1: Requirement Analysis & Planning - 100% Completed

### 1. Understanding Business Requirements
**Current Manual Process:**
- Customer creates a Case via Email/Web.
- Support Agent manually reads subject & description and sets priority (Low, Medium, High).
- Manager manually assigns cases to agents based on availability.

**Key Problems Identified:**
1. High volume (500+ tickets/day) leads to delay.
2. Critical tickets are often missed due to manual reading.
3. No standard for priority - depends on agent judgment.
4. Uneven workload distribution among agents.
5. SLA breach and low customer satisfaction.
6. No real-time visibility for managers.

**Business Need:** A Salesforce-based automated system that uses AI to predict priority and auto-assign cases.

### 2. Defining Project Scope & Objectives
**In Scope:**
- Custom fields in Case object: Predicted Priority, Priority Score, Issue Category.
- Record-Triggered Flow for auto-assignment logic.
- Agentforce Service Agent for priority prediction.
- Reports & Dashboards for managers.
- Role-based security model.

**Out of Scope (Phase 2):**
- Email-to-Case integration
- Chatbot integration

**Objectives:**
- Reduce ticket response time by 40%
- Achieve 90% accuracy in priority prediction
- Ensure equal workload distribution
- Improve CSAT score

### 3. Gathering & Analyzing User Needs
**Support Agent Needs:**
- Auto-assigned tickets only relevant to their skill.
- Clear priority and SLA deadline visible.
- Easy case closure process.

**Support Manager Needs:**
- Dashboard showing Open Cases by Priority, Agent Workload, SLA Breach.
- Ability to re-assign cases.
- Reports for performance analysis.

**Customer Needs:**
- Faster resolution for urgent issues.
- Status updates on their cases.

**Admin Needs:**
- Easy configuration of assignment rules.
- Secure data access.

### 4. Identifying Key Salesforce Features & Tools Required
1.  **Salesforce Objects:** Case, Account, Contact, User, Queue
2.  **Custom Fields:** Predicted_Priority__c (Picklist), Priority_Score__c (Number), Issue_Category__c (Picklist), Case_Account_ID__c (Text)
3.  **Automation:** Record-Triggered Flow (for auto assignment), Validation Rules
4.  **AI:** Agentforce - Service Agent to analyze case description and predict priority
5.  **Security:** Profiles, Roles (Support Agent, Support Manager), Sharing Rules, Queues
6.  **Analytics:** Reports & Dashboards
7.  **Research Tools Used:** ChatGPT, Google Search, Salesforce Trailhead, Salesforce Help Docs

### 5. Designing Data Model and Security Model

**Data Model Design:**
- **Case Object (Main):**
    - Standard Fields: CaseNumber, Subject, Description, Status, Origin, Priority
    - Custom Fields: Predicted_Priority__c, Priority_Score__c, Issue_Category__c, SLA_Deadline__c
- **Account & Contact:** Linked to Case
- **User & Queue:** Owner of Case

**Security Model Design:**
- **Profiles:** 
    - Support Agent Profile - Can Create/Edit own cases only
    - Support Manager Profile - Can View/Edit All Team Cases
- **Roles:** 
    - Support Manager (Parent Role)
    - Support Agent (Child Role)
- **OWD:** Case = Private (so agents see only own cases)
- **Queues:** Created for - Billing Queue, Technical Queue, Critical Queue
- **Sharing:** Manager can see all cases via Role Hierarchy.

**Approach Summary:**
Phase 1 is completed by gathering requirements from real support scenarios, defining clear scope, and designing a scalable data and security model in Salesforce that will be implemented in Phase 2.
