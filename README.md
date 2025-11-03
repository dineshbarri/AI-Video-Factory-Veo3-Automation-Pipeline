
<div align="center">

<!-- Wave Divider -->
<img src="https://capsule-render.vercel.app/api?type=wave&color=6366f1&height=150&section=header" />

<!-- Main Title -->
<h1>🎬 AI Video Factory Automator</h1>

<!-- Subtitle with typing effect -->
<p>
  <img src="https://readme-typing-svg.herokuapp.com/?font=Fira+Code&size=16&duration=3000&pause=1000&color=6366F1&center=true&vCenter=true&width=435&lines=Automated+Video+Production+Pipeline;Google+Veo3+Powered;Multi-Platform+Publishing;AI+Driven+Content+Creation" alt="Typing SVG" />
</p>

<!-- BADGES -->
<img src="https://img.shields.io/badge/n8n-Workflow-orange?style=for-the-badge&logo=n8n" alt="n8n">
<img src="https://img.shields.io/badge/Google-Veo3-blue?style=for-the-badge&logo=google" alt="Google Veo3">
<img src="https://img.shields.io/badge/YouTube-Upload-red?style=for-the-badge&logo=youtube" alt="YouTube">
<img src="https://img.shields.io/badge/AI-Generated-success?style=for-the-badge&logo=openai" alt="AI">
<img src="https://img.shields.io/badge/License-MIT-green?style=for-the-badge" alt="License">
</div>

---
## 🚀 Overview

The **AI Video Factory** is a modular, production-ready automation workflow that:
- Generates **AI videos via Veo3** (Google Vertex AI)
- Automatically creates **captions, hashtags, and titles** using Gemini (PaLM)
- Uploads results to **Google Drive**
- Logs metadata in **Google Sheets**
- Publishes to **YouTube** automatically
- Sends Succesfully Created  emails via **Gmail**

---

## 🧩 Key Features

| Feature | Description |
|----------|-------------|
| 🎥 **AI Video Generation** | Generates unique, cinematic videos from text prompts using Google Veo3. |
| 🧠 **AI Caption & Title Builder** | Uses Gemini / PaLM to generate optimized YouTube titles, tags, and hashtags. |
| ☁️ **Drive & Sheet Integration** | Stores videos and logs metadata automatically. |
| 📊 **Smart Wait & Retry Logic** | Adaptive retry mechanism for long-running API operations. |
| 🔐 **Secure Credential System** | Built with environment variables or OAuth2 best practices. |
| 🎬 **Youtube Upload** | Uploads “Video” to a social platform with preview links. |
| 📧 **Email Notifications** | Sends creative “Video Ready” messages with preview links. |

---

<div align = "center">
	
## ⚙️ Workflow Architecture

<p align="center">
  <img src="assets/video_creation_pipeline.png"  width=" 400 " alt="AI Video Creation Pipeline">
	<br>
  <em>End-to-End Automated Video Production Pipeline</em>
</p>

</div>

---



<div align="center">

##  🖼️ Workflow Demo

![Workflow Overview](assets/workflow-overview.png)
*Complete n8n workflow showing the end-to-end automation pipeline*
</div>

**🧭 Workflow Path:**
Schedule Trigger → Idea Generator → Gemini → Veo3 API → Drive → YouTube → Sheets → Gmail


---

<div align="center">

### 1. Idea Generation Pipeline

<br>
<img src="assets/idea_generator.png" width="650" style="border-radius:14px;border:4px solid #4FD1C5;box-shadow:0 12px 35px rgba(79,209,197,0.4);margin:15px 0">
<br> AI-powered creative concept generation


#### **↓ Output ↓**

<br>
<img src="assets/idea_output.png"  style="border-radius:14px;border:4px solid #48BB78;box-shadow:0 12px 35px rgba(72,187,120,0.4);margin:15px 0">
<br> Structured Data in Google Sheets
</div>


**Generated Fields:**
- **Caption**: Viral-ready title with emoji and hashtags
- **Idea**: Concise concept under 13 words
- **Environment**: Visual setting description
- **Status**: "for production" flag





<div align="center" >

### 2. 🎬 Veo3 Video Generation Core

<!-- MAIN FLOW DIAGRAM -->
<img src="assets/veo3_video_generation.png" width="600" 
style="border-radius:16px;border:3px solid #4FD1C5;
box-shadow:0 12px 35px rgba(79,209,197,0.4);
margin:20px 0;">
<p style="font-size:14px;color:#6B7280;margin-top:5px;">
🧩 Connected workflow — <em>Cinematic Prompt Builder → Veo3 API Setup → Generate Veo3 Video → Render Status Check</em>
</p>

---

### ⚙️ Output 1 — Prompt Generation & API Setup

<img src="assets/veo3_output.png" width="600"
style="border-radius:14px;border:3px solid #48BB78;
box-shadow:0 10px 28px rgba(72,187,120,0.35);
margin:15px 0;">

<p align="center" style="font-size:14px;color:#4B5563;">
🧠 <strong>Cinematic Prompt Builder</strong> crafts rich, story-driven prompts.<br>
⚙️ <strong>API Setup</strong> defines <code>project_id</code>, <code>region</code>, and <code>endpoint</code> — preparing Veo3 for the magic.
</p>

### ⚡ Output 2 — Video Generation & Render Status

<img src="assets/veo3_rendered_output.png" width="600"
style="border-radius:14px;border:3px solid #48BB78;
box-shadow:0 10px 28px rgba(72,187,120,0.35);
margin:15px 0;">

<p align="center" style="font-size:14px;color:#4B5563;">
🎬 <strong>Generate Veo3 Video</strong> submits your cinematic prompt to Vertex AI.<br>
⏳ <strong>Render Status Check</strong> tracks progress until your AI video is fully generated.
</p>

---
<p style="font-size:13px;color:#6B7280;">
💡 <em>This two-step visualization clearly shows the transition from creative AI prompt → API configuration → real-time video generation and render completion.</em>
</p>

</div>

---

<div align="center">

### 3. 🔁 Smart Retry System & Failure Handling

<p style="font-size:16px;color:#374151;">
Resilient automation built to recover from API delays and failures — ensuring every Veo3 render completes or gracefully notifies you.
</p>

<!-- MAIN FLOW IMAGE -->
<img src="assets/smart_wait_system.png" width="600"
style="border-radius:16px;border:3px solid #60A5FA;
box-shadow:0 12px 35px rgba(96,165,250,0.4);
margin:20px 0;">
<p style="font-size:14px;color:#6B7280;margin-top:5px;">
🧩 Workflow Segment — <em>Max Retry Counter → Wait Node → Veo3 Status Check → Failure Email</em>
</p>


### ⏳ Output 1 — Retry Logic in Action

<img src="assets/wait_system_output.png" width="590"
style="border-radius:14px;border:3px solid #3B82F6;
box-shadow:0 10px 28px rgba(59,130,246,0.35);
margin:15px 0;">

<p align="center" style="font-size:14px;color:#4B5563;">
🔄 <strong>Retry Counter</strong> tracks the number of render attempts.<br>
⏱️ <strong>Wait Node</strong> introduces smart intervals (e.g., 30s → 60s → 120s).<br>
🧠 This adaptive delay ensures Veo3 has enough time to process large video jobs.
</p>

### 📧 Output 2 — Failure Notification Alert

<img src="assets/failure_mail.png" width="600"
style="border-radius:14px;border:3px solid #F87171;
box-shadow:0 10px 28px rgba(248,113,113,0.35);
margin:15px 0;">

<p align="center" style="font-size:14px;color:#4B5563;">
🚨 After <strong>Max Retries</strong> are reached, the workflow triggers a <strong>Failure Email Notification</strong>.<br>
📩 The message includes <em>Idea Name, Operation ID, Retry Count, and Timestamp</em> — making debugging effortless.
</p>

</div>

---



<div align="center">

## ⚖️ Success vs Failure Flow

<img src="assets/success_failure_flow.png" width="600"
style="border-radius:16px;border:3px solid #E5E7EB;
box-shadow:0 10px 30px rgba(0,0,0,0.08);margin:20px 0;">

<p style="font-size:14px;color:#4B5563;max-width:600px;margin:0 auto;">
This visual clearly differentiates the two possible outcomes of the <strong>Smart Retry System</strong>.<br>
🟢 <strong>Success Path</strong> — smooth render completion, uploads, and success notifications.<br>
🔴 <strong>Failure Path</strong> — intelligent retries followed by a Gmail alert if the job fails.
</p>

</div>

---



<div align="center">

### 4. ☁️ File Processing & Upload

<p style="font-size:16px;color:#374151;">
From AI-rendered data to published content — this segment converts, uploads, and organizes your video files seamlessly across Google services.
</p>

<!-- MAIN FLOW IMAGE -->
<img src="assets/file_processing_upload.png" width="600"
style="border-radius:16px;border:3px solid #38BDF8;
box-shadow:0 12px 35px rgba(56,189,248,0.4);
margin:20px 0;">
<p style="font-size:14px;color:#6B7280;margin-top:5px;">
🧩 Workflow Segment — <em>Base64 → MP4 Conversion → Drive Upload → YouTube Upload → Data Merge for Logging</em>
</p>

--- 

### 🎞️ Output 1 — Base64 to MP4 Conversion

<img src="assets/base64_to_mp4_output.png" width="600"
style="border-radius:14px;border:3px solid #0EA5E9;
box-shadow:0 10px 28px rgba(14,165,233,0.35);
margin:15px 0;">

<p align="center" style="font-size:14px;color:#4B5563;">
💾 The <strong>Base64 → MP4 Converter</strong> node decodes raw Veo3 output into a playable video file.<br>
🧱 Prepares the final media for parallel uploads and metadata handling.
</p>

---

### ☁️ Output 2 — Google Drive Upload

<img src="assets/drive_upload_output.png" width="600"
style="border-radius:14px;border:3px solid #10B981;
box-shadow:0 10px 28px rgba(16,185,129,0.35);
margin:15px 0;">

<p align="center" style="font-size:14px;color:#4B5563;">
📂 The <strong>Google Drive Upload</strong> node stores the generated MP4 in your designated Drive folder.<br>
✅ Automatically assigns file names with timestamps and project tags.
</p>

---

### 📺 Output 3 — YouTube Upload with Metadata

<img src="assets/youtube_upload_output.png" width="600">

<p align="center" style="font-size:14px;color:#4B5563;">
🎬 The <strong>YouTube Upload</strong> node publishes videos directly with AI-generated <em>title, description, hashtags, and thumbnail</em>.<br>
🚀 End-to-end automated publishing in one click.
</p>
	
</div>

---



<div align="center" >

### 5. 🧾 Data Logging & Success Notification

<p style="font-size:16px;color:#374151;">
Every successful video is logged, tracked, and celebrated — with automated data entry and a personalized success email.
</p>

<!-- MAIN FLOW IMAGE -->
<img src="assets/logging_notification.png" width="750"
style="border-radius:16px;border:3px solid #A78BFA;
box-shadow:0 12px 35px rgba(167,139,250,0.4);
margin:20px 0;">
<p style="font-size:14px;color:#6B7280;margin-top:5px;">
🧩 <em>Data Merge → Google Sheets Log → Gmail Success Notification</em>
</p>
</div>

---

## 🎥 Output — YouTube Upload & Gmail Success 

<table align="center" style="width:100%; border-collapse:collapse;">
<tr>

<!-- LEFT GIF: Gmail Notification -->
<td style="width:50%; text-align:center; vertical-align:top; padding:10px;">
<h3 style="color:#C084FC;">✉️ Gmail Success Notification</h3>
<img src="assets/gmail_success.gif" 
style="border-radius:12px; border:3px solid #C084FC; box-shadow:0 8px 24px rgba(192,132,252,0.35); height:300px; object-fit:cover;">
<p style="font-size:13px; color:#6B7280; margin-top:6px;">
Automated success email with video details and preview links.
</p>
</td>

<!-- RIGHT GIF: YouTube Upload -->
<td style="width:50%; text-align:center; vertical-align:top; padding:10px;">
<h3 style="color:#EF4444;">📺 YouTube Upload</h3>
<img src="assets/youtube_upload.gif" 
style="border-radius:12px; border:3px solid #EF4444; box-shadow:0 8px 24px rgba(239,68,68,0.35); height:300px;width:100%; object-fit:cover;">
<p style="font-size:13px; color:#6B7280; margin-top:6px;">
Seamless AI-to-YouTube upload — fully automated with title, caption, and tags.
</p>
</td>

</tr>
</table>

</div>

---

## 🔧 Core Modules & Nodes

| Module | Purpose | Key Nodes |
|--------|----------|-----------|
| 💡 **Idea Input** | Accepts text prompts or creative ideas. | Google Sheets Trigger / Manual Input |
| 🧠 **Gemini Caption Generator** | Uses Gemini / PaLM to generate titles, captions, and hashtags. | Gemini Text Generation Node |
| 🎬 **Veo3 Video Generation** | Sends requests to Google Vertex AI’s Veo3 model. | HTTP Request Node (POST → Vertex AI Endpoint) |
| ⏳ **Smart Wait & Retry System** | Waits for `operationName` completion from Vertex AI. | Function Node + Wait Node |
| 💾 **Google Drive Upload** | Uploads final MP4 from Veo3 response to Drive. | Google Drive Upload Node |
| 📺 **YouTube Upload** | Publishes approved videos directly to YouTube with metadata. | YouTube Upload Node |
| 📋 **Google Sheets Logger** | Logs metadata: idea, caption, operationName, links, timestamps. | Google Sheets Append Row Node |
| ✉️ **Gmail Notification** | Sends a success email with video preview, title, and review buttons. | Gmail Send Email Node |

---

## 🧩 Client Setup Guide

- ***Before running the workflow, configure your API credentials securely.***

- **Use the interactive  Client Setup Guide 🌐  to walk through the step-by-step onboarding process and securely link your API credentials with n8n.**

<p align="center">
  <a href="https://unrivaled-chaja-4615f0.netlify.app/" target="_blank" rel="noopener noreferrer">
    <img src="https://img.shields.io/badge/Open%20Client%20Setup%20Guide-blue?style=for-the-badge&logo=google-chrome&logoColor=white" alt="Open Client Setup Guide">
  </a>
</p>

> 🧱 All credentials should be created within the n8n Credentials Manager — never hardcode secrets in the workflow.

---
## 🗂 Repository Structure
```
AI-Video-Factory-Veo3/
│
├── 📄 README.md
├── 🧠 AI Video Factory Automator-Veo3.json # main n8n workflow
├── ⚙️ LICENSE
├── 🧩 assets/
│ ├── workflow-overview.png
│ ├── execution-demo.png
│ ├── veo3-generation.png
│ ├── youtube-publishing.png
│ ├── email-notification.png
│ └── video_creation_pipeline.png
└── 📁 docs/
├── client_setup_guide.html
├── package.json
└── Troubleshooting.md
```


## 🛠️ Installation

Follow these steps to set up and run the **AI Video Factory — Veo3 Automation Pipeline** on your system:

### 1️⃣ Clone the Repository
- Clone the repository to your local environment and navigate into the project folder.

``` 
    git clone https://github.com/dineshbarri/AI-Video-Factory-Veo3-Automation-Pipeline.git
    cd AI-Video-Factory-Veo3-Automation-Pipeline
```
###  2️⃣ Import the Workflow into n8n

-  Open your n8n instance (Cloud or Local).  
-  Click **Import Workflow → Upload JSON**, and select the file:  
   **`AI Video Factory Automator-Veo3.json`**
  -  Once imported, the workflow nodes and credentials structure will load automatically into your n8n dashboard.
### 3️⃣ Configure Credentials



<p align="center"> <a href="https://unrivaled-chaja-4615f0.netlify.app/" target="_blank" rel="noopener noreferrer"> <img src="https://img.shields.io/badge/🚀_Launch_Interactive_Setup_Guide-6366f1?style=for-the-badge&logo=google-chrome&logoColor=white" alt="Setup Guide"> </a> </p>

### 4️⃣ Test & Verify
```
✅ All credentials connected
✅ Google Sheets logging active  
✅ Drive uploads working
✅ YouTube publishing live
✅ Email notifications sending
```
---
## 💰 Cost Optimization

### 🎯 Performance Metrics
- ⚡ Generation Time: 2-5 minutes per video
- ✅ Success Rate: 95%+ with smart retry logic
- 📊 Monthly Capacity: 500+ videos
- 🔄 Retry Attempts: 0-2 average with progressive backoff
- 📱 Output Quality: 9:16 HD mobile-optimized format

### 📈 Estimated Costs
| Service | Cost per Video | Monthly (100 videos) |
|----------|----------|----------------|
| Veo3 API | ~$0.20 | $20.00 |
| Gemini API | ~$0.01 | $1.00 |
| Storage | ~$0.05 | $5.00 |
| Total | ~$0.26 | $26.00 |

---
## 📞 Need Help?
###  [![🐛 Create Issue](https://img.shields.io/badge/📝_Create_Issue-Open_Here-success?style=for-the-badge&logo=github)](https://github.com/dineshbarri/AI-Video-Factory-Veo3-Automation-Pipeline/issues/new/choose)
---

## 📜 License
This project is licensed under the **MIT License** - see the [LICENSE](LICENSE) file for complete details.

**MIT License © 2025 Dinesh Barri**
 
---
## 👤 Author

 #### &nbsp; Dinesh Barri

-  [![GitHub](https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white)](https://github.com/dineshbarri)
-  [![Linkedin](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/dinesh-barri-7654b010b)
---

## ⭐ Feedback & Contributions
- 🐛 Report Bugs - Create detailed issue reports
- 💡 Suggest Features - Share your ideas for improvement
- 🔧 Submit PRs - Code improvements and new features
- 📚 Improve Docs - Better documentation and examples


