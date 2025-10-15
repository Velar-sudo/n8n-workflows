# 🧩 Form Submission Webhook – Version 2

## 📘 Overview
This workflow (`Form submission_html_ver2.json`) demonstrates how to collect user data through a simple **HTML form** and automatically send it to **n8n** via a **Webhook node**.  
It’s designed for users who want to integrate **front-end web forms** with n8n automation — perfect for contact forms, sign-up forms, or lightweight data capture tools.

---

## ⚙️ Prerequisites

Before running this workflow, if you are running n8n locally, ensure you have:
- ✅ **n8n** running locally (`http://localhost:5678`)
- ✅ Workflow **activated** in n8n (⚡ toggle ON)
- ✅ An **active webhook URL** from the Webhook node (use the **production** URL, not test)
- ✅ A text editor (VS Code, Nano, etc.)
- ✅ A browser (any will do)

---

## 🧱 Workflow Structure
- **Webhook Trigger:**  Listens for form submissions (JSON payloads from your HTML form).
- **Edit Node:** Transforms and sanitizes inputs for downstream systems.
- **Airtable:** Records submitted data (Name, Email, Occupation, Message).

---

## 🧩 How It Works

1. The HTML form collects user data.
2. When submitted, the form sends a **POST request** to your n8n Webhook endpoint.
3. n8n captures the data and stores it in **Airtable**.
4. A confirmation message (or JSON response) is sent back to the browser.

---

## 🖥️ Demo Frontend

The sample form HTML file is located at: https://github.com/Velar-sudo/n8n-workflows/blob/main/Assets/form(test).htm

You can test the form locally or host it temporarily to simulate submissions.

---

## 💻 Running the Test

🟩 Step 1: Activate the Workflow

 - In n8n, toggle your workflow to Active.
 - Copy the production webhook URL (http://your-webhook-url).

🟦 Step 2: Open the Form

 - Open the (https://github.com/Velar-sudo/n8n-workflows/blob/main/Assets/form(test).htm) file in your browser.
 - Fill in the fields and click Send.

 🟨 Step 3: Check Results

 - Go to your Airtable base — the submission should appear as a new record.
 - You’ll also see the execution in your n8n Executions List.

---

🧠 Tips

 - Ensure the action attribute in your form matches your n8n production webhook URL.

 - Avoid using test URLs for browser forms — they only work in n8n’s test mode.

 - To deploy this online, replace localhost with your public server or tunnel URL (e.g., via ngrok).
 - If your HTML form isn’t opening directly or submitting correctly from your file system, run a **local web server** with Python:

 # For Python 3
```bash
python3 -m http.server 5500

```
Then open your browser and visit:
http://localhost:5500/Assets/form(test).htm

This hosts your HTML file locally and ensures the form can properly send data to n8n.

---

🏁 Summary

This version shows how to connect front-end forms directly to n8n automations.
It’s perfect for building simple data capture systems, customer inquiries, or form-based integrations without any backend code.

---

## 🔁 Improvements Over v1

- Cleaner node connections and naming
- Optimized response message for frontend

---
🧩 Built with ❤️ by Velar-sudo using n8n


Author: Velar-sudo
Version: 2.0
Workflow File: Form submission_html_ver2.json
Created With: n8n Local Instance (Linux Mint)
