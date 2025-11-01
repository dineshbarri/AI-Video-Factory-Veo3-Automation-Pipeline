# 🎬 AI Video Factory — Veo3 Automation Workflow (n8n + Google Vertex AI)

[![n8n](https://img.shields.io/badge/Built%20With-n8n-orange)](https://n8n.io)
[![Google Cloud](https://img.shields.io/badge/Powered%20By-Google%20Vertex%20AI-blue)](https://cloud.google.com/vertex-ai)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
<p align="center">
  <img src="assets/demo_screenshot.png" width="700" alt="AI Video Factory demo preview">
</p>

> **A fully automated AI video generation system** using [n8n](https://n8n.io), [Google Vertex AI (Veo3)](https://cloud.google.com/vertex-ai), and Gemini for captions — capable of creating, storing, reviewing, and publishing AI-generated videos end-to-end.  

---

## 🚀 Overview

The **AI Video Factory** is a modular, production-ready automation workflow that:
- Generates **AI videos via Veo3** (Google Vertex AI)
- Automatically creates **captions, hashtags, and titles** using Gemini (PaLM)
- Uploads results to **Google Drive**
- Logs metadata in **Google Sheets**
- Sends **review/approval emails** via Gmail
- Publishes to **YouTube** automatically (or after manual review)

---

## 🧩 Key Features

| Feature | Description |
|----------|-------------|
| 🎥 **AI Video Generation** | Generates unique, cinematic videos from text prompts using Google Veo3. |
| 🧠 **AI Caption & Title Builder** | Uses Gemini / PaLM to generate optimized YouTube titles, tags, and hashtags. |
| ☁️ **Drive & Sheet Integration** | Stores videos and logs metadata automatically. |
| 📧 **Email Notifications** | Sends creative “Video Ready” messages with preview links. |
| 🪄 **Hold-for-Review Webhook** | Optional manual approval before publishing to YouTube. |
| 📊 **Smart Wait & Retry Logic** | Adaptive retry mechanism for long-running API operations. |
| 🔐 **Secure Credential System** | Built with environment variables and OAuth2 best practices. |

---

## ⚙️ Workflow Architecture

<p align="center">
  <img src="assets/architecture_diagram.png" width="720">
</p>

1. **Idea Source (Google Sheet / Form)** → captures video ideas  
2. **Gemini Caption Generator** → creates creative captions & hashtags  
3. **Veo3 Renderer** → generates MP4 videos (via Vertex AI endpoint)  
4. **Smart Wait Node** → monitors render progress  
5. **Drive Upload** → stores rendered video securely  
6. **Google Sheets Logger** → appends record with metadata & links  
7. **Email Notification Node** → sends preview & review buttons  
8. **Hold-for-Review Webhook** → one-click approval to publish  
9. **YouTube Upload Node** → publishes automatically once approved  

---

## 🧭 Credential Setup Guide

Before running, connect your API credentials securely.  
Use the included **[Credential_Setup_Wizard.html](./Credential_Setup_Wizard.html)** for an interactive step-by-step setup.

| Service | Purpose | Credential Type |
|----------|----------|----------------|
| Google Cloud | Veo3 model & Vertex AI API | Service Account (JSON) |
| YouTube | Video upload | OAuth2 |
| Gemini (PaLM) | Captions & metadata | API Key |
| Drive & Sheets | File storage & logging | OAuth2 |
| Gmail | Notifications | OAuth2 |

> 🧱 All credentials should be created within the n8n Credentials Manager — never hardcode secrets in the workflow.

---

## 🔁 Review Flow

Each rendered video can be manually approved before publishing.  
The system generates a **unique review token** stored in Google Sheets.

### ✉️ Example Email

> **Subject:** 🎬 Your AI Video is Ready!  
> **Buttons:** ✅ Publish | ❌ Reject  
> **Webhook:** [n8n_webhook/hold-review](#)

Once the “Publish” button is clicked:
- Workflow validates the secure token  
- Downloads the video from Drive  
- Uploads it to YouTube  
- Updates the status in Google Sheet  

---

## 🛠️ Installation

1. Clone this repo  
   ```bash
   git clone https://github.com/YOUR-USERNAME/AI-Video-Factory-Veo3.git
   cd AI-Video-Factory-Veo3
