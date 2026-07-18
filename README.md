# ms-foundry-it-support-agent

## Project Description

This project demonstrates how to build an end-to-end AI agent solution using **Microsoft Foundry**, **Azure AI Agents**, **Visual Studio Code**, and **Python**.

The solution creates an intelligent **IT Support Agent** for Contoso Corporation that can answer employee technical questions using enterprise knowledge sources, analyze system performance data, and generate insights using AI-powered tools.

The agent uses:

* **File Search** for grounded responses from IT policy documentation
* **Code Interpreter** for data analysis and visualization
* **Microsoft Foundry Portal** for agent creation and configuration
* **Foundry Toolkit for VS Code** for development workflows
* **Azure AI Projects SDK** for programmatic interaction

---

## Solution Overview

The project builds an AI-powered IT support assistant capable of:

* Answering employee IT policy questions
* Searching enterprise documentation for accurate responses
* Analyzing system performance metrics
* Detecting trends and anomalies in operational data
* Creating charts and visualizations
* Providing interactive conversations through a Python application

Architecture:

```text
                    User
                      |
                      |
              Python Client App
                      |
                      |
          Azure AI Projects SDK
                      |
                      |
          Microsoft Foundry AI Agent
                      |
        +-------------+-------------+
        |                           |
    File Search              Code Interpreter
        |                           |
 IT Policy Documents       Performance CSV Data
```

---

# Features

## Enterprise Knowledge Grounding

The agent uses uploaded IT policy documentation to provide accurate answers.

Example questions:

```
What is the policy for password resets?
```

```
How do I request new software?
```

---

## Data Analysis with Code Interpreter

The agent can analyze uploaded performance data.

Example:

```
Analyze the system performance data and identify periods where CPU usage exceeded 80%.
```

The agent can:

* Calculate statistics
* Identify trends
* Compare metrics
* Generate charts

---

## Visualization Generation

The agent can create visual reports.

Example:

```
Create a line chart showing memory usage trends over time.
```

Generated files are saved locally in:

```
agent_outputs/
```

---

# Technology Stack

| Technology            | Purpose                       |
| --------------------- | ----------------------------- |
| Microsoft Foundry     | AI agent development platform |
| Azure AI Agents       | Agent runtime                 |
| Azure AI Projects SDK | Python integration            |
| Python 3.13+          | Client application            |
| Visual Studio Code    | Development environment       |
| Foundry Toolkit       | VS Code integration           |
| File Search           | Knowledge retrieval           |
| Code Interpreter      | Data analysis                 |

---

# Repository Structure

```text
ms-foundry-it-support-agent/

│
├── README.md
├── requirements.txt
├── .env.example
├── .gitignore
│
├── src/
│   └── agent_with_functions.py
│
├── data/
│   ├── IT_Policy.txt
│   └── system_performance.csv
│
├── agent_outputs/
│   └── .gitkeep
│
└── docs/
    └── architecture.md
```

---

# Prerequisites

Before running this project, ensure you have:

* Azure subscription
* Microsoft Foundry project
* Python 3.13 or later
* Visual Studio Code
* Git
* Azure CLI

Install Azure CLI:

```bash
az login
```

---

# Create Microsoft Foundry Project

1. Open Microsoft Foundry:

```
https://ai.azure.com
```

2. Create a new project.

Example:

```
it-support-agent-project
```

3. Create an agent:

```
Agent Name:
it-support-agent
```

4. Configure agent instructions:

```
You are an IT Support Agent for Contoso Corporation.

You help employees with technical issues and IT policy questions.

Guidelines:
- Always be professional and helpful
- Use IT policy documentation to answer questions accurately
- If you don't know the answer, suggest contacting IT support
- Collect required information before creating tickets
```

---

# Configure Agent Tools

Enable:

## File Search

Upload:

```
data/IT_Policy.txt
```

This provides enterprise knowledge grounding.

---

## Code Interpreter

Upload:

```
data/system_performance.csv
```

This enables:

* Data analysis
* Statistical calculations
* Visualization generation

---

# Local Development Setup

Clone repository:

```bash
git clone <repository-url>

cd ms-foundry-it-support-agent
```

Create Python environment:

```bash
python -m venv labenv
```

Activate environment:

Windows:

```powershell
.\labenv\Scripts\Activate.ps1
```

Linux/macOS:

```bash
source labenv/bin/activate
```

Install dependencies:

```bash
pip install -r requirements.txt
```

---

# Environment Configuration

Create a copy of:

```
.env.example
```

Rename:

```
.env
```

Update:

```env
PROJECT_ENDPOINT=<your-foundry-project-endpoint>

AGENT_NAME=it-support-agent
```

The project endpoint can be copied from:

* Microsoft Foundry Portal
* Foundry Toolkit extension in VS Code

---

# Run the Application

Start the agent client:

```bash
python src/agent_with_functions.py
```

Expected output:

```text
Connecting to Microsoft Foundry project...

Connected to agent: it-support-agent

IT Support Agent Ready!

Ask questions, request data analysis, or get help.
```

---

# Test the Agent

## Test Knowledge Retrieval

Prompt:

```
What's the policy for password resets?
```

Expected behavior:

The agent searches IT policy documentation and provides the correct procedure.

---

## Test Software Request Policy

Prompt:

```
How do I request new software?
```

Expected behavior:

The agent retrieves software installation guidelines.

---

## Test Data Analysis

Prompt:

```
Analyze the system performance data and identify CPU usage problems.
```

Expected behavior:

The agent:

* Reads CSV data
* Performs analysis
* Provides insights

---

## Test Visualization

Prompt:

```
Create a chart showing CPU usage over time.
```

Expected behavior:

The agent generates a visualization and saves it:

```
agent_outputs/chart_1.png
```

---

# Example Use Cases

This pattern can be extended for:

* IT helpdesk automation
* Enterprise knowledge assistants
* Data analysis agents
* Operations monitoring assistants
* Internal employee support bots

---

# Security Considerations

Recommended production improvements:

* Use Azure Managed Identity instead of local credentials
* Apply least-privilege Azure RBAC roles
* Protect environment variables
* Monitor agent usage and costs
* Validate uploaded enterprise documents

---

# Cleanup

To avoid unnecessary Azure charges:

1. Open Microsoft Foundry Portal
2. Navigate to the project
3. Delete the project

or remove the Azure resource group:

```bash
az group delete --name <resource-group-name>
```

---

# Learning Objectives

After completing this project, you will understand:

* How to create AI agents with Microsoft Foundry
* How to ground agents with enterprise data
* How to use File Search and Code Interpreter tools
* How to connect Python applications with AI agents
* How to build practical enterprise AI solutions

---

# License

This project is intended for educational and demonstration purposes.
