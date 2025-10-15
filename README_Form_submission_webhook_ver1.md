# 🧩 Form Submission Webhook — Version 1

## 📘 Overview
**Form Submission Webhook (ver1)** is an automated n8n workflow designed to handle form submissions efficiently.  
It collects user data through a webhook, processes it, and stores it in an **Airtable** base.  

> 🧠 In short: this workflow listens for incoming POST requests from any form, cleans up the input fields, and records them neatly in your Airtable table.

---

## 🧱 Workflow Structure

### **1. Webhook Node**
- **Method:** `POST`
- **Path:** `/form-submission`
- Captures incoming form data (e.g., name, email, occupation, message).

### **2. Edit Fields Node**
- Cleans and organizes incoming data.
- Simplifies JSON structure before sending it to Airtable.

### **3. Airtable Node**
- **Operation:** `Create`
- Automatically inserts the submitted form data into your Airtable base.
- Fields include:
  - Full name  
  - Email  
  - Occupation  
  - Message  

---

## ⚙️ Setup Instructions

### **Step 1: Import the Workflow**
1. Open your n8n instance.
2. Go to **Workflows → Import from File**.
3. Upload `Form_submission_webhook_ver1.json`.

### **Step 2: Connect Your Credentials**
1. In the **Airtable** node, add your own **Airtable Personal Access Token**.
2. Ensure you link it to your correct base and table.

> ⚠️ Credentials are **not** included in this workflow file for security reasons.

---

## 🚀 Running the Workflow

### **Option 1 — Run via Terminal (Local n8n Instance)**

#### **Linux & macOS**
```bash
n8n start
```

## 🧠 How It Works

1. When the workflow is active, the **Webhook Node** exposes a local URL.
2. A POST request is sent to that URL from a terminal
3. The **Function Node** processes the data and forwards it.
4. The **Airtable Node** saves the incoming information to your configured table.

---

## 🖥️ How to Execute (Platform Guide)

### **For Linux / macOS Users**

Open your terminal and run:

```bash
curl -X POST "Use your webhook-url" \
-H "Content-Type: application/json" \
-d '{"name":"velar Sudo","email":"velar@example.com","message":"Hello Doe!"}'

If successful, the terminal should return: {"message":"Workflow was started"}
You’ll then see the new record appear in your Airtable base.

### **For Windows Users**

Use this command in PowerShell (adjusted syntax for Windows):
Open your terminal and run: 

```powershell
curl -Method POST http://your-webhook `
  -H "Content-Type: application/json" `
  -Body '{"name":"Velar Sudo","email":"velar@example.com","message":"Hello Doe!"}'
  ```

Expected output: Workflow was started

### **Note**

Use /webhook-test/ when testing the workflow.

Once you activate it, n8n switches to the production URL:
http://your-webhook-url

🔒 Remember: Inactive workflows do not execute.
You must activate it in n8n for the webhook to respond.

### **Airtable Setup** 
1. Create an Airtable base with columns like:
    Name

    Email

    Occupation

    Message

2. In your Airtable node:
   - Choose your "Base ID" and "Table Name".
   - Map each field to match the incoming webhook data.

   ### **🏁 Next Steps**

 - Explore Form submission_html_ver2.json
   to connect this webhook to an HTML form page instead of manual curl requests.

 - Add environment variables for your Airtable API key using n8n credentials for better security.

Author: Velar-sudo
Workflow: Form_sub_ver1
Platform: n8n (Localhost)
Version: 1.0.0
Last Updated: October 2025
