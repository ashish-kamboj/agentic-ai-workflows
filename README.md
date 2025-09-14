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

| Workflow Name | Description | Inputs | Outputs | Special Notes |
|--------------|-------------|--------|---------|--------------|
|[wf_update_google_doc.json](https://github.com/ashish-kamboj/agentic-ai-workflows/blob/main/n8n/wf_update_google_doc.json)| Workflow that automatically updates Google Docs based on chat messages. It uses an AI agent with Ollama's Llama 3.2 model to process incoming chat messages and then inserts the AI-generated output into a specified Google Document. | **Chat Message:** Any text sent to the chat trigger | **Google Document Update:** The AI agent's output is automatically inserted into the specified Google Doc | **Ollama API:** Uses "Ollama account" credential for local LLM access <br> **Google Docs OAuth2:** Uses "Google cloud account" credential for document access|
|[wf_get_output_using_llm.json](https://github.com/ashish-kamboj/agentic-ai-workflows/blob/main/n8n/wf_get_output_using_llm.json) |The workflow enables interactive conversations where users can send messages and receive AI-generated responses with memory retention capabilities. |**Chat Message:** Any text sent to the chat trigger | LLM generated response | **Ollama API:** Uses "Ollama account" credential for local LLM access |
|[wf_send_message_to_telegram_bot.json](https://github.com/ashish-kamboj/agentic-ai-workflows/blob/main/n8n/wf_send_message_to_telegram_bot.json) | The workflow receives messages through a chat interface, processes them with an AI agent, and sends the responses directly to a specific Telegram chat. It combines conversational AI capabilities with Telegram messaging integration. |**Chat Message:** Any text sent to the chat trigger | **Telegram Message:** AI-generated responses sent to Telegram | **Ollama API:** Uses "Ollama account" credential for local LLM access <br> **Telegram bot:** Valid Telegram bot token must be configured |
|[wf_daily_workflow_backup_to_github.json](https://github.com/ashish-kamboj/agentic-ai-workflows/blob/main/n8n/wf_daily_workflow_backup_to_github.json) | This workflow is designed to automatically backup n8n workflows to a GitHub repository on a daily basis. It compares the current state of workflows in n8n with their previously backed-up versions in GitHub and only updates files that have changed or creates new files for new workflows. | **Trigger:** Scheduled trigger (configured to run daily) | **GitHub Files:** JSON files containing workflow definitions saved to the GitHub repository | **GitHub API Credentials:** Required for repository access <br> **n8n API Credentials:** Required to fetch workflow data |

<!-- Add your n8n workflows below. Copy and modify the row above for each workflow. -->

---

## crewAI Workflows

Below is a table listing all available crewAI workflows in this repository. This format helps users easily discover and use workflows relevant to their needs.

<table style="width:100%">
  <colgroup>
    <col style="width: 10%">
    <col style="width: 45%">
    <col style="width: 12.5%">
    <col style="width: 12.5%">
    <col style="width: 20%">
  </colgroup>
  <thead>
    <tr>
      <th>Workflow Name</th>
      <th>Description</th>
      <th>Inputs</th>
      <th>Outputs</th>
      <th>Special Notes</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="https://github.com/ashish-kamboj/agentic-ai-workflows/blob/main/crewai/wf_agent_to_research_and_write_article.ipynb">Agent to research and write article</a></td>
      <td>Automate the process of researching, writing, and editing a blog article. It defines three agents—Content Planner, Content Writer, and Editor—each with specific roles and tasks. The workflow includes planning content, writing a draft, and editing for quality and style, all powered by LLMs.</td>
      <td>Research topic</td>
      <td>Structured research summary</td>
      <td>
        <ol>
          <li>Uses the ollama/llama3.2:3b model via the Ollama API, which can be set up locally and is free to use.</li>
          <li>Agents are implemented with CrewAI and interact with the local LLM for fast,</li>
          <li>The tasks are performed sequentially.</li>
        </ol>
      </td>
    </tr>
    <tr>
      <td><a href="https://github.com/ashish-kamboj/agentic-ai-workflows/blob/main/crewai/wf_agent_for_web_scrapping_and_summarization.ipynb">Agent for web scrapping and summarization</a></td>
      <td>Demonstrates how to use CrewAI agents and tools to scrape content from a web page and summarize it using a locally hosted Ollama LLM. The workflow includes initializing the scraping tool, setting up the agent, defining the task, and running the crew to get the summary.</td>
      <td>Provide website URL to scrape while initializing <b>ScrapeWebsiteTool()</b></td>
      <td>Structured summary of the scrapped content</td>
      <td>
        <ol>
          <li>Uses the ollama/llama3.2:3b model via the Ollama API, which can be set up locally and is free to use.</li>
          <li>Agents are implemented with CrewAI and interact with the local LLM for fast, private inference.</li>
        </ol>
      </td>
    </tr>
    <tr>
      <td><a href="https://github.com/ashish-kamboj/agentic-ai-workflows/blob/main/crewai/wf_agent_for_travel_recommendation_with_mlflow_integration.ipynb">Agent for travel recommendation with mlflow integration</a></td>
      <td>Demonstrates integration between CrewAI and MLflow for tracking AI agent workflows. Creates a travel recommendation system that suggests the best city for photography travel and provide 5-day photography itinerary</td>
      <td>No Input as such, it's part of prompt only but can be passed as input</b></td>
      <td>5-day photography itenary for the choosed city</td>
      <td>
        <ol>
          <li>Uses the ollama/llama3.2:3b model via the Ollama API, which can be set up locally and is free to use.</li>
          <li>Agents are implemented with CrewAI and interact with the local LLM for fast, private inference.</li>
          <li>Used MLflow, which provides a tracing feature that enhances LLM observability by capturing detailed information about the execution of application’s services. Tracing provides a way to record the inputs, outputs, and metadata associated with each intermediate step of a request, enabling you to easily pinpoint the source of bugs and unexpected behaviors.</li>
        </ol>
      </td>
    </tr>
    <tr>
      <td><a href="https://github.com/ashish-kamboj/agentic-ai-workflows/blob/main/crewai/wf_agent_for_summarization_and_translation_using_grok.ipynb">Agent for Summarization and Translation using Grok</a></td>
      <td>Demonstrates a simple two-agent workflow using CrewAI:Documentation-Summarizer produces a concise summary and Technical Translator converts the summary to Hindi</b></td>
      <td>No Input as such, it's part of prompt only but can be passed as input</b></td>
      <td>Text Summary and translation in choosen or provided language</td>
      <td>
        <ol>
          <li>Uses groq/llama-3.3-70b-versatile LLM model, In order to use generate grok API Key from https://console.groq.com/keys</li>
          <li>Agents are implemented with CrewAI and interact with the Grok LLM for fast inference.</li>
        </ol>
      </td>
    </tr>
  </tbody>
</table>



---