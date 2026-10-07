# 🏥 Patient Assistance System

An AI-powered **Patient Assistance System** built using **UiPath Agentic AI, Maestro BPMN, UiPath Apps, Human-in-the-Loop (HITL), and RPA**.

The system collects patient information, analyzes reported symptoms, determines severity, routes the case to a doctor for approval, and automatically sends an appropriate email based on the doctor's decision.

> **Note:** This project is designed as an automation and assistance system. It does not provide medical diagnosis or treatment recommendations.

---

## 🚀 Project Overview

The Patient Assistance System automates the initial patient assistance workflow using multiple specialized AI agents and human approval.

The system follows an end-to-end workflow:

```text
Patient Details
      │
      ▼
Query Assistance Agent
      │
      ▼
Severity Analysis Agent
      │
      ▼
Doctor Approval App
      │
      ├────────────── Approve ──────────────┐
      │                                     ▼
      │                            Email Generation Agent
      │                                     │
      │                                     ▼
      │                                 Send Email
      │
      └────────────── Reject ──────────────┐
                                            ▼
                                  Email Rejection Agent
                                            │
                                            ▼
                                        Send Email 2
```

---

# 🔄 Complete Workflow

## 1️⃣ Patient Information

The process starts with patient details.

The system accepts:

- Patient Name
- Age
- Gender
- Symptoms
- Symptoms Duration
- Email

These details are passed into the **Query Assistance Agent**.

---

## 2️⃣ Query Assistance Agent

The **Query Assistance Agent** performs the initial analysis of the patient's reported information.

Its purpose is to organize and summarize the information provided by the patient.

### Input

```text
Patient Name
Age
Gender
Symptoms
Symptoms Duration
Email
```

### Output

The agent produces:

- Patient information
- Reported symptoms
- Symptom duration
- General observations

The agent is designed to remain grounded in the information supplied by the patient and avoid generating a medical diagnosis.

---

## 3️⃣ Severity Analysis Agent

The output from the Query Assistance Agent is passed to the **Severity Analysis Agent**.

It then generates:

```text
Severity
Action
```

The severity analysis helps determine how the case should proceed through the workflow.

---

# 4️⃣ Doctor Approval App

After severity analysis, the case is sent to the **Doctor Approval App**.

This is the **Human-in-the-Loop (HITL)** stage of the automation.

The doctor can review information such as:

- Patient Name
- Age
- Gender
- Symptoms
- Symptoms Duration
- Severity

The doctor then selects:

```text
Approve
```

or

```text
Reject
```

This ensures that the final decision is not made entirely by AI.

---

# 5️⃣ Approval Branch

If the doctor selects **Approve**, the workflow moves to the:

### Email Generation Agent

This agent generates a patient email using the available information.

The email contains the relevant patient details and the recommended action.

The generated email body is then passed to the **Send Email** RPA process.

---

# 6️⃣ Send Email

The **Send Email** automation uses UiPath's Gmail integration to send the generated patient communication.

The email includes:

- Patient information
- Analysis information
- Action/recommendation

The email subject used in the workflow is:

```text
Patient Analysis Report
```

---

# 7️⃣ Rejection Branch

If the doctor selects **Reject**, the workflow moves to the:

### Email Rejection Agent

This agent generates a rejection email based on the provided patient information and the action/reason for rejection.

The generated email is then passed to the **Send Email 2** RPA process.

---

# 8️⃣ Send Rejection Email

The **Send Email 2** automation sends the rejection notification to the patient's email address.

The email subject used in the workflow is:

```text
Application Status
```

This completes the rejection branch.

---

# 🤖 AI Agents Used

The project contains multiple specialized AI agents.

| Agent | Purpose |
|---|---|
| Query Assistance Agent | Analyzes and summarizes reported patient information |
| Severity Analysis Agent | Evaluates symptoms and symptom duration |
| Email Generation Agent | Generates the approval/analysis email |
| Email Rejection Agent | Generates the rejection email |

---

# 👨‍⚕️ Human-in-the-Loop

A key feature of this project is **Human-in-the-Loop approval**.

Instead of allowing the AI system to make the final decision independently, the case is sent to a doctor through the **Doctor Approval App**.

```text
AI Analysis
     ↓
Severity Analysis
     ↓
Doctor Review
     ↓
 ┌───┴────┐
 ▼        ▼
Approve  Reject
```

This combines AI-based analysis with human decision-making.

---

# ⚙️ RPA Components

The project uses RPA processes for email communication.

### Send Email

Used for sending the generated approval/analysis email.

### Send Email 2

Used for sending the rejection notification.

Both processes use **Gmail integration through UiPath Integration Service**.

---

# 🔗 Maestro BPMN

The complete workflow is orchestrated using **UiPath Maestro BPMN**.

Maestro coordinates:

- AI Agent execution
- Data passing between agents
- Human approval
- Conditional branching
- Email generation
- RPA execution

This allows the complete process to work as one end-to-end automation.

---

# 🛠️ Technologies Used

- **UiPath Studio Web**
- **UiPath Agentic AI**
- **UiPath Maestro**
- **Maestro BPMN**
- **UiPath Apps**
- **Human-in-the-Loop (HITL)**
- **RPA**
- **Gmail Integration**
- **AI Agents**
- **Workflow Automation**

---

# 🎯 Project Objective

The objective of this project is to demonstrate how **Agentic AI, Human-in-the-Loop, UiPath Apps, Maestro, and RPA** can be combined to automate a real-world assistance workflow.

The project focuses on using AI for information processing while keeping a human decision-maker involved before the final communication is sent.

---
