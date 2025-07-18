# WorkwiseAI

## 🤖 Project Assignment Automation System

This system automates the assignment of the most suitable employee (agent) to a newly created project based on their skills, availability, past performance, and leave status. The project integrates tools like **Jira**, **HRMS**, **LLM Guard**, and **Langfuse** to ensure efficient task management, employee utilization, and AI safety.



## 📌 Table of Contents

- [Overview](#-overview)
- [Architecture](#-architecture)
- [Key Features](#-key-features)
- [Technology Stack](#-technology-stack)
- [Data Flow](#-data-flow)
- [Security (LLM Guard)](#-security-llm-guard)
- [LLM Usage Tracking (Langfuse)](#-llm-usage-tracking-langfuse)
- [Setup Instructions](#-setup-instructions)
- [Environment Variables](#-environment-variables)
- [Future Enhancements](#-future-enhancements)
- [License](#-license)



## 📖 Overview

When a new project request is created (e.g., via Jira), the system intelligently selects the best-suited employee based on:

- **Employee’s experience** (tracked in Jira)
- **Average completion time** of past projects
- **Current availability or leave status** (fetched from HRMS)

The selected employee is then automatically assigned to the project, reducing manual workload and improving efficiency.

This system also ensures **LLM interaction security** and **cost monitoring** using dedicated tools:

- 🛡 **LLM Guard**: To protect prompt interactions
- 📊 **Langfuse**: To monitor usage and cost of LLM APIs



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
|  LLM Guard & Langfuse       |
+-----------------------------+

```

## 🚀 Key Features

- ✅ Automated agent assignment based on live data
- 🔄 Jira + HRMS integration
- 🔐 Prompt & output security with LLM Guard
- 📊 Token usage & cost tracking with Langfuse
- 🔍 Employee performance analytics



## ⚙️ Technology Stack

| Component       | Technology                          |
|-----------------|--------------------------------------|
| Backend         | Python / Node.js                     |
| Task Manager    | Jira (REST API)                      |
| HR Data Source  | HRMS (e.g., Odoo or custom API)      |
| AI Security     | LLM Guard                            |
| LLM Monitoring  | Langfuse                             |
| Optional LLM    | OpenAI / Anthropic / Local LLM       |
| Database        | PostgreSQL / MongoDB (optional)      |



## 🔄 Data Flow

1. **Project ticket** is created in Jira.
2. System queries **employee performance** from Jira and **leave status** from HRMS.
3. **Matching logic** selects the best-suited employee.
4. The selected employee is **automatically assigned** to the ticket.
5. If LLM is used for processing:
   - Prompt is passed through **LLM Guard**
   - Request is tracked using **Langfuse**



## 🔐 LLM Security – LLM Guard

LLM Guard is used to:

- 🛡 Prevent prompt injection
- 🚫 Mask sensitive data
- 🧼 Sanitize output for safety

It ensures all LLM interactions are protected before reaching the model.



## 📊 LLM Usage Tracking – Langfuse

Langfuse provides:

- 🔢 Token usage per prompt
- 💸 Cost tracking by user, model, or session
- ⏱ Performance metrics
- 📈 Visual analytics dashboard

Langfuse integration helps manage your LLM budget efficiently.


## 📈 Future Enhancements

- 🤖 **AI Model Scoring**  
  Enhance employee-project matching using AI-based embeddings and scoring algorithms.

- 🗓️ **Visual Leave Planner Integration**  
  Integrate a calendar-style dashboard to visualize employee availability and approved leaves.

- 🔔 **Slack / Microsoft Teams Notifications**  
  Notify employees or teams directly in communication tools when a new project is assigned.

- 🧩 **Modular HRMS Plug-ins**  
  Allow easy integration with various HRMS platforms (Odoo, Zoho, SAP, etc.) via plugin architecture.


## 🤝 Contributing

We welcome contributions from the community! To contribute:

1. **Fork** this repository.
2. **Create a new branch** for your feature or fix.  
   Example: `feature/improve-matching-logic`
3. **Make your changes** and ensure the app runs smoothly.
4. **Submit a pull request** with a clear description of your changes.

> All contributions are reviewed and merged based on code quality and alignment with the project goals.



## 📝 License

This project is licensed under the **MIT License**.  
See the [LICENSE](LICENSE) file for details.



## 📬 Contact

- 📧 **Email:** [support@yourcompany.com](mailto:support@yourcompany.com)  
- 🐙 **GitHub:** [github.com/your-username](https://github.com/your-username)

