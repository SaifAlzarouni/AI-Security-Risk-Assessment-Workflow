# AI Security Risk Assessment Workflow

> An AI-powered n8n workflow that summarizes PDF documents and meeting notes, identifies cybersecurity risks, ranks them by severity, and automatically creates a professional Gmail draft using Google Gemini.

![License](https://img.shields.io/badge/License-MIT-green.svg)
![n8n](https://img.shields.io/badge/Built%20with-n8n-orange)
![Google Gemini](https://img.shields.io/badge/AI-Google%20Gemini-blue)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen)

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
