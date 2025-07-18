# WorkwiseAI

## 🤖 Project Assignment Automation System

This system automates the assignment of the most suitable employee (agent) to a newly created project based on their skills, availability, past performance, and leave status. The project integrates tools like **Jira**, **HRMS**, a **Security Layer**, and **LLM Monitoring** to ensure efficient task management, employee utilization, and AI safety.

---

## 📌 Table of Contents

- [Overview](#-overview)
- [Architecture](#-architecture)
- [Key Features](#-key-features)
- [Technology Stack](#-technology-stack)
- [Data Flow](#-data-flow)
- [Security Layer](#-security-layer)
- [LLM Monitoring](#-llm-monitoring)
- [Setup Instructions](#-setup-instructions)
- [Environment Variables](#-environment-variables)
- [Future Enhancements](#-future-enhancements)
- [License](#-license)

---

## 📖 Overview

When a new project request is created (e.g., via Jira), the system intelligently selects the best-suited employee based on:

- **Employee’s experience** (tracked in Jira)
- **Average completion time** of past projects
- **Current availability or leave status** (fetched from HRMS)

The selected employee is then automatically assigned to the project, reducing manual workload and improving efficiency.

This system also ensures **LLM interaction security** and **usage monitoring** using:

- 🛡 A **Security Layer** to protect prompt interactions
- 📊 An **LLM Monitoring** tool to track usage and costs

---

## 🔧 Workflow Diagram

```text
+------------------------+
|   New Project (Jira)   |
+----------+-------------+
           |
           v
+------------------------+
| Fetch All Employees    |
| (from HRMS + Jira)     |
+----------+-------------+
           |
           v
+------------------------+
| Apply Assignment Logic |
| - Skill match          |
| - Past performance     |
| - Availability status  |
+----------+-------------+
           |
           v
+------------------------+
| Assign Ticket in Jira  |
+----------+-------------+
           |
           v
+-----------------------------+
| LLM Integration (Optional)  |
+-----------------------------+
           |
           v
+-----------------------------+
|  Security Layer &           |
|  LLM Monitoring             |
+-----------------------------+
```

## 🚀 Key Features

- ✅ Automated agent assignment based on live data
- 🔄 Jira + HRMS integration
- 🔐 Prompt & output security with Security Layer
- 📊 Token usage & cost tracking with LLM Monitoring
- 🔍 Employee performance analytics



## ⚙️ Technology Stack

| Component       | Technology                                 |
|-----------------|--------------------------------------------|
| Backend         | Python / Node.js / Html / CSS / Javascript |                   |
| Task Manager    | Jira (REST API)                            |
| HR Data Source  | HRMS             | 
| AI Security     | Security Layer                                |
| LLM Monitoring  | LLM Monitoring                                  |
| Optional LLM    | OpenAI / Anthropic / Local LLM             |
| Database        | PostgreSQL / MongoDB (optional)            |



## 🔄 Data Flow

1. **Project ticket** is created in Jira.
2. System queries **employee performance** from Jira and **leave status** from HRMS.
3. **Matching logic** selects the best-suited employee.
4. The selected employee is **automatically assigned** to the ticket.
5. If LLM is used for processing:
   - Prompt is passed through **LLM Guard**
   - Request is tracked using **Langfuse**



## 🔐 LLM Security

LLM Guard is used to:

- 🛡 Prevents prompt injection
- 🚫 Masks sensitive data
- 🧼 Sanitizes prompts and responses

It ensures all LLM interactions are protected before reaching the model.



## 📊 LLM Usage Tracking 

Langfuse provides:

- 🔢 Token usage per prompt
- 💸 Cost tracking by user, model, or session
- ⏱ Performance metrics
- 📈 Visual analytics dashboard


## 📈 Future Enhancements

- 🤖 **AI Model Scoring**  
  Enhance employee-project matching using AI-based embeddings and scoring algorithms.

- 🗓️ **Visual Leave Planner Integration**  
  Integrate a calendar-style dashboard to visualize employee availability and approved leaves.

- 🔔 **Slack / Microsoft Teams Notifications**  
  Notify employees or teams directly in communication tools when a new project is assigned.

- 🧩 **Modular HRMS Plug-ins**  
  Allow easy integration with various HRMS platforms (Odoo, Zoho, SAP, etc.) via plugin architecture.


## 📝 License

This project is licensed under the **MIT License**.  
See the [LICENSE](LICENSE) file for details.



## 📬 Contact

- 📧 **Email:** [support@yourcompany.com](mailto:support@yourcompany.com)  
- 🐙 **GitHub:** [github.com/your-username](https://github.com/your-username)

