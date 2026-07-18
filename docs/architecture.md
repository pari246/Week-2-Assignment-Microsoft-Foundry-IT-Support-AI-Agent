# Microsoft Foundry IT Support AI Agent Architecture

## Overview

This project demonstrates an AI-powered IT Support Agent built using Microsoft Foundry and Azure AI Agent capabilities.

The agent helps Contoso employees by answering IT questions, searching company documentation, analyzing operational data, and generating insights.

---

# Solution Architecture

```text
                 User
                   |
                   |
                   v
        Python Agent Client Application
                   |
                   |
                   v
          Azure AI Projects SDK
                   |
                   |
                   v
        Microsoft Foundry AI Agent
                   |
        +----------+----------+
        |                     |
        v                     v
   File Search          Code Interpreter
        |                     |
        v                     v
 IT Policy Document   System Performance CSV
