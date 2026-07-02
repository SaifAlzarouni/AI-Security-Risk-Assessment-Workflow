# AI Security Risk Assessment Workflow

> An AI-powered n8n workflow that summarizes PDF documents and meeting notes, identifies cybersecurity risks, ranks them by severity, and automatically creates a professional Gmail draft using Google Gemini.

![License](https://img.shields.io/badge/License-MIT-green.svg)
![n8n](https://img.shields.io/badge/Built%20with-n8n-orange)
![Google Gemini](https://img.shields.io/badge/AI-Google%20Gemini-blue)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen)

## Table of Contents

- [Project Overview](#project-overview)
- [Key Features](#key-features)
- [Software Development Methodology](#software-development-methodology)
- [System Architecture](#system-architecture)
- [Workflow Diagram](#workflow-diagram)
- [Technologies Used](#technologies-used)
- [Software Requirements](#software-requirements)
- [Input](#input)
- [Output](#output)
- [Installation](#installation)
- [Usage](#usage)
- [Folder Structure](#folder-structure)
- [Example Workflow Output](#example-workflow-output)
- [Future Improvements](#future-improvements)
- [License](#license)
- [Author](#author)

---

## Project Overview

Organizations often review long audit reports, compliance documents, and meeting notes to identify important security issues. Manually reading and summarizing these documents can take time and may delay important follow-up actions.

This project automates that process using n8n and Google Gemini. The workflow accepts meeting notes or a PDF document, extracts the document content, generates a clean executive summary, identifies key cybersecurity risks, ranks them by severity, and creates a professional Gmail draft that is ready for review.

The goal of this project is to demonstrate how workflow automation and generative AI can be combined to improve document review, cybersecurity analysis, and business communication.

---

## Key Features

* Accepts PDF documents and meeting notes as input
* Extracts text from uploaded PDF files
* Generates an executive summary, key points, and action items
* Uses a second AI agent to identify cybersecurity risks
* Classifies risks as Critical, High, or Medium
* Prioritizes the top three risks
* Generates a concise professional email draft
* Automatically creates the draft in Gmail
* Uses a modular multi-agent workflow design

---

## Software Development Methodology

This project was developed using an Agile-inspired iterative development approach. Each component of the workflow was designed, tested, and improved individually before integrating the complete automation.

### Development Phases

1. Requirement Analysis
   - Define the project objective
   - Identify workflow inputs and outputs
   - Determine automation requirements

2. Workflow Design
   - Design the n8n workflow architecture
   - Create the document processing pipeline
   - Define interactions between AI agents

3. AI Prompt Engineering
   - Develop prompts for document summarization
   - Develop prompts for cybersecurity risk assessment
   - Optimize prompts for consistent structured outputs

4. Integration
   - Connect Google Gemini AI
   - Configure Gmail draft generation
   - Configure PDF text extraction

5. Testing
   - Test using sample meeting notes
   - Test using PDF documents
   - Verify generated summaries
   - Verify risk classifications
   - Verify Gmail draft formatting

6. Documentation
   - Prepare workflow documentation
   - Capture workflow screenshots
   - Document installation and usage instructions

This iterative methodology allowed each workflow component to be validated independently before combining them into the final automation.

---

# System Architecture

The workflow is composed of six main stages that work together to automate cybersecurity document analysis.

```text
PDF / Meeting Notes
        │
        ▼
 PDF Text Extraction
        │
        ▼
 AI Agent 1
(Document Summarization)
        │
        ▼
 AI Agent 2
(Risk Assessment)
        │
        ▼
 Gmail Draft Generation
        │
        ▼
 Professional Security Email
```

## Workflow Diagram

![Workflow Overview](images/workflow-overview.png)

The workflow first extracts text from the uploaded document, generates an executive summary, identifies cybersecurity risks using a dedicated AI agent, prioritizes the most critical findings, and finally prepares a professional Gmail draft ready for review.

---

# Technologies Used

| Technology | Purpose |
|------------|---------|
| n8n | Workflow automation platform |
| Google Gemini | AI document summarization and cybersecurity risk analysis |
| Gmail | Automatic email draft generation |
| PDF Extract Node | Extracts text from uploaded PDF documents |
| JavaScript Expressions | Parse AI outputs for Gmail subject and message |
| Markdown | Project documentation |

---

# Software Requirements

The following software and services are required to run this project:

- n8n (latest stable version)
- Google Gemini API access
- Gmail account
- Gmail OAuth credentials configured in n8n
- Internet connection
- Modern web browser

---

# Input

The workflow accepts either of the following inputs:

### Option 1 — PDF Document

A PDF containing:

- Security audit reports
- Compliance reports
- Meeting minutes
- Risk assessment reports
- Technical documentation

### Option 2 — Meeting Notes

Plain text meeting notes describing security findings, audit observations, or operational updates.

---

# Output

After processing, the workflow automatically generates:

- Executive Summary
- Key Points
- Action Items
- Top 3 Cybersecurity Risks
- Risk Level (Critical / High / Medium)
- Recommended Mitigations
- Professional Gmail Draft

The Gmail draft is automatically created and saved for user review before sending.

---

# Installation

Follow these steps to run the AI Security Risk Assessment Workflow.

## 1. Clone the Repository

```bash
git clone https://github.com/SaifAlzarouni/AI-Security-Risk-Assessment-Workflow.git
```

## 2. Install n8n

Install the latest version of n8n by following the official installation guide:

https://docs.n8n.io/

## 3. Import the Workflow

1. Open n8n.
2. Select **Import Workflow**.
3. Import the file located in:

```
workflow/AI-Document-Meeting-Assistant.json
```

## 4. Configure Credentials

Create the required credentials inside n8n:

- Google Gemini API
- Gmail OAuth2

## 5. Test the Workflow

Upload one of the sample PDF files from:

```
sample-files/
```

or provide meeting notes manually.

The workflow will automatically generate:

- Executive Summary
- Key Findings
- Action Items
- Cybersecurity Risk Assessment
- Gmail Draft

---

# Usage

Once the workflow has been imported and configured, the automation can be executed by following these steps.

## Step 1 — Start the Workflow

Open n8n and activate the workflow.

## Step 2 — Provide Input

Choose one of the supported inputs:

- Upload a PDF document
- Enter meeting notes

## Step 3 — AI Document Analysis

The first AI Agent analyzes the document and automatically generates:

- Executive Summary
- Key Points
- Action Items

## Step 4 — Cybersecurity Risk Assessment

The second AI Agent reviews the generated summary and:

- Identifies cybersecurity risks
- Assigns a severity level
- Prioritizes the three most critical risks
- Generates mitigation recommendations

## Step 5 — Gmail Draft Generation

The workflow automatically extracts the generated subject and email body and creates a Gmail draft.

The draft is saved for user review before sending.

## Workflow Summary

```
Input
   │
   ▼
PDF / Meeting Notes
   │
   ▼
Extract Text
   │
   ▼
AI Agent (Summary)
   │
   ▼
AI Agent (Risk Assessment)
   │
   ▼
Generate Gmail Draft
   │
   ▼
Ready for Review
```

---

# Folder Structure

```
AI-Security-Risk-Assessment-Workflow
│
├── README.md                     # Main project documentation
│
├── workflow/
│   ├── AI-Document-Meeting-Assistant.json
│   └── README.md
│
├── images/
│   ├── workflow-overview.png
│   ├── pdf-extraction-node.png
│   ├── ai-agent-summary-prompt.png
│   ├── risk-agent-prompt-part1.png
│   ├── risk-agent-prompt-part2.png
│   ├── gmail-draft-preview.png
│   └── README.md
│
└── sample-files/
    └── README.md
```

The repository is organized to separate workflow files, documentation, screenshots, and sample resources, making the project easier to understand and maintain.

---

# Screenshots

The following screenshots demonstrate the workflow configuration, AI prompts, execution process, and generated results.

## Complete Workflow

This diagram shows the overall n8n workflow used in the project.

![Workflow Overview](images/workflow-overview.png)

---

## PDF Text Extraction

The workflow extracts text from uploaded PDF documents before passing the content to the AI agents.

![PDF Extraction](images/pdf-extraction-node.png)

---

## AI Agent – Document Summarization Prompt

The first AI Agent is responsible for generating the executive summary, key points, action items, and email draft.

![AI Agent Prompt](images/ai-agent-summary-prompt.png)

---

## AI Agent – Cybersecurity Risk Assessment Prompt

The second AI Agent analyzes the generated summary and identifies the three highest-priority cybersecurity risks.

![Risk Assessment Prompt Part 1](images/risk-agent-prompt-part1.png)

![Risk Assessment Prompt Part 2](images/risk-agent-prompt-part2.png)

---

## Workflow Output

Example output generated by the document summarization AI Agent.

![Summary Output 1](images/summary-output-part1.png)

![Summary Output 2](images/summary-output-part2.png)

![Summary Output 3](images/summary-output-part3.png)

---

## Risk Assessment Output

Example output generated by the cybersecurity risk assessment AI Agent.

![Risk Assessment Output 1](images/risk-assessment-output-part1.png)

![Risk Assessment Output 2](images/risk-assessment-output-part2.png)

---

## Gmail Draft

The final workflow automatically creates a professional Gmail draft for review.

![Gmail Draft Preview](images/gmail-draft-preview.png)

---

# Future Improvements

Possible enhancements for future versions of this project include:

- Support for additional document formats (DOCX, TXT, HTML)
- Integration with Microsoft Outlook in addition to Gmail
- Support for multiple AI models (OpenAI, Claude, Azure OpenAI)
- Automatic generation of PDF security reports
- Dashboard for tracking previously analyzed documents
- Export results to Excel or CSV
- Risk trend analysis across multiple documents
- User authentication and role-based access control
- Cloud deployment using Docker and Kubernetes
- Automatic notification through Microsoft Teams or Slack

---

# License

This project is licensed under the MIT License.

See the [LICENSE](LICENSE) file for more information.

---

# Acknowledgements

This project was developed as a personal portfolio project to demonstrate workflow automation, AI-powered document analysis, and cybersecurity risk assessment using n8n and Google Gemini.

Special thanks to:

- The n8n community for workflow automation resources.
- Google Gemini for AI-powered text analysis.
- GitHub for project hosting and version control.
