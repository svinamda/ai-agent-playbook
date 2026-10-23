### n8n Workflows

This directory contains the production automation and orchestration blueprints for the project. These workflows are maintained as version-controlled JSON files exported directly from n8n. 

### 🚀 Getting Started

### 1. Importing a Workflow

To deploy or inspect any workflow in this directory: 

1. Open your **n8n instance** dashboard.
2. Create a new, blank workflow.
3. Click on the **three dots (...)** menu in the top-right corner.
4. Select **Import from File** and choose the relevant .json file from this folder.

### 2. Exporting Updates

When you make changes to a workflow in the n8n UI, make sure to update this repository: 

1. Click the **three dots (...)** menu in the top-right corner of the n8n workflow canvas.
2. Select **Download** to get the updated JSON file.
3. Overwrite the corresponding file in this directory and commit the changes.

### 🔑 Credentials & Environment Variables

[!WARNING]
**Never commit raw credentials, API keys, or passwords to this repository.** 

n8n decouples workflow logic from authentication data. When you import these files: 

* **Missing Credentials:** You will see a warning icon on nodes requiring authentication (e.g., Slack, Postgres, OpenAI). You must link your own secure credentials within your local n8n instance.
* **Environment Variables:** Workflows utilizing expressions like {{ $env["VARIABLE_NAME"] }} expect those values to be defined in your n8n host environment (e.g., your .env file if running via Docker Compose).

### 🛠️ Production Best Practices

* **Active/Inactive Status:** Ensure production workflows are explicitly toggled to **Active** inside n8n to enable their triggers (Webhooks, Cron schedules, etc.).
* **Error Trigger Node:** It is highly recommended to attach an **Error Trigger** node to production workflows to catch failures and route alerts to a monitoring channel (e.g., Slack or email).
