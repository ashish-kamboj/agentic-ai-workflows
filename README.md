# Agentic AI Workflows

This repository is a curated collection of agentic AI workflows built using [n8n](https://n8n.io/) and [crewAI](https://crewai.com/). It serves as a resource for developers, researchers, and enthusiasts interested in leveraging agent-based automation and orchestration using these powerful platforms.

## Overview

- **n8n workflows**: Visual, low-code automations that can connect APIs, data, and logic for AI-driven operations.
- **crewAI workflows**: Programmatic agent orchestration for complex, multi-step, or multi-agent tasks in Python.

Both workflow types enable you to build, customize, and run agentic pipelines for a wide range of use cases—such as data enrichment, content creation, task delegation, research agents, and more.

---

## Repository Structure

```
agentic-ai-workflows/
├── n8n/
│   └── ...         # n8n workflow JSON files
├── crewai/
│   └── ...         # crewAI workflow Python scripts
├── README.md
└── LICENSE
```

- Put your **n8n workflow files** (exported as .json) inside the `n8n/` directory.
- Place your **crewAI Python scripts** (typically ending with `.py`) inside the `crewai/` directory.

---

## Getting Started

### 1. Using n8n Workflows

1. **Install n8n:**  
   Refer to the [n8n documentation](https://docs.n8n.io/hosting/installation/) for installation instructions (Docker, npm, desktop app, etc.).

2. **Import a Workflow:**  
   - Go to the n8n editor UI.  
   - Click "Import" and upload the desired workflow JSON from this repo's `n8n/` folder.  
   - Configure any required credentials or environment variables.

3. **Run or Schedule the Workflow:**  
   - Trigger manually or set up schedules/webhooks as needed.

### 2. Using crewAI Workflows

1. **Set up Python environment:**  
   - Install Python 3.9+ (ideally in a virtual environment).  
   - Install crewAI:
     ```bash
     pip install crewai
     ```

2. **Run a Workflow:**  
   - Open the desired Python script from the `crewai/` directory.  
   - Review and adjust any required prompts, agent definitions, or credentials.  
   - Run the script:
     ```bash
     python path/to/your_workflow.py
     ```

---

## n8n Workflows

Below is a table listing all available n8n workflows in this repository. This makes it easy to browse, search, and understand what each workflow does at a glance.

| Workflow Name | File | Description | Inputs | Outputs | Special Notes |
|--------------|------|-------------|--------|---------|--------------|
| _Example: Lead Enrichment_ | n8n/lead-enrichment.json | Enriches CRM leads using LinkedIn and email APIs | Lead name, email | Enriched lead profile | Requires LinkedIn and email API credentials |

<!-- Add your n8n workflows below. Copy and modify the row above for each workflow. -->

---

## crewAI Workflows

Below is a table listing all available crewAI workflows in this repository. This format helps users easily discover and use workflows relevant to their needs.

| Workflow Name | File | Description | Inputs | Outputs | Special Notes |
|--------------|------|-------------|--------|---------|--------------|
| _Example: Research Agent Crew_ | crewai/research_crew.py | Multi-agent research and report generation workflow | Research topic, sources | Structured research summary | Adjust agent prompts as needed |

<!-- Add your crewAI workflows below. Copy and modify the row above for each workflow. -->

---