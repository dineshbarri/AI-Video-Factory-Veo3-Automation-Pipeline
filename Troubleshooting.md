
---

## ⚙️ `Troubleshooting.md`

```markdown
# 🩺 AI Video Factory — Troubleshooting & Debug Guide

> This document lists the most common issues, failure scenarios, and solutions for your **AI Video Factory (Veo3)** workflow.

---

## 🧱 Common Setup Issues

| Problem | Likely Cause | Solution |
|----------|---------------|----------|
| ❌ **Credential errors in nodes** | Missing or expired OAuth tokens | Reconnect affected credentials in n8n → Credentials panel |
| ⚠️ **403 Forbidden from Veo3 API** | Service account missing role | Ensure roles: `Vertex AI User`, `Storage Object Admin` |
| 📄 **Invalid JSON key** | Key copied incorrectly | Recreate service account key in Google Cloud Console |
| 🧩 **Gemini request fails** | API key expired or not linked to billing | Regenerate Gemini key in AI Studio |
| 🗂️ **Drive upload error** | Folder not shared or incorrect permission | Share Drive folder with connected OAuth account |
| 🧾 **Sheets append error** | Sheet ID mismatch | Verify Sheet ID in node settings matches the intended document |
| 📧 **Gmail send failure (400)** | Unverified app | Verify OAuth client or enable “Test User” in Google Cloud credentials |
| 📺 **YouTube upload quota exceeded** | Daily limit reached | Wait 24 hours or switch to another authorized YouTube account |

---

## 🔁 Workflow Execution Failures

### 1️⃣ **“Predict operation not found”**
**Cause:** Veo3 operationName expired or invalid.  
**Fix:**
- Ensure you save the `operationName` immediately after job creation.  
- Retry with a fresh request if older than 12 hours.  
- Add retry node with conditional stop after 6 attempts.

---

### 2️⃣ **“Smart Wait Timeout”**
**Cause:** Video render exceeded expected time.  
**Fix:**
- Increase `maxAttempts` or `waitTimes` array.  
- Add logging to Sheets (`attemptCount`, `timestamp`, `status`).  
- If persistent, contact Google Cloud support — check `operation.error` message.

---

### 3️⃣ **“Upload to YouTube failed (403)”**
**Cause:** Token expired or YouTube account disconnected.  
**Fix:**
- Reconnect YouTube OAuth in n8n → reauthorize account.  
- Check channel access (Owner or Editor role).  

---

### 4️⃣ **“Webhook not triggered from email buttons”**
**Cause:** URL encoded characters / token mismatch.  
**Fix:**
- Ensure the button URLs are properly encoded in HTML.  
- Verify that the webhook path matches `/hold-review`.  
- Check Google Sheet token column matches URL parameter.

---

### 5️⃣ **“Drive upload succeeded, but video corrupt”**
**Cause:** Base64 video bytes not properly converted.  
**Fix:**
- Confirm you decode base64 → binary before upload.  
- Add checksum (`bytesBase64Encoded` length or MD5) for integrity validation.

---

### 6️⃣ **“Sheets row missing YouTube URL”**
**Cause:** Workflow didn’t update after publish.  
**Fix:**
- Add Update Row node after YouTube upload.  
- Map `videoId` and `youtubeUrl` explicitly.  

---

## 🧰 Debugging Tips

- Use **Execute Node** in n8n to isolate problem areas.  
- Inspect **Execution Logs** → look for red “Error” labels.  
- Add a “Debug Console” function node:
  ```js
  console.log($json);
  return items;
