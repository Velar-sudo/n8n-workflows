# 🧩 Form Submission Webhook – Version 3 (Postman)

## 📘 Overview
This workflow (`Form_submission_postman_ver3.json`) demonstrates how to use **Postman** to send form data directly to an **n8n Webhook**, simulating a real web form submission.
It’s ideal for **testing workflows, debugging webhooks**, or **developing APIs** before building a front-end interface.

---

## ⚙️ Prerequisites

Before running this workflow, make sure you have:

- ✅ **n8n** running locally (`http://localhost:5678`)

- ✅ The workflow **activated** (⚡ toggle ON)

- ✅ **Postman Desktop Agent** installed (needed for localhost requests)

- ✅ Internet connection (Postman uses it for network calls)

---

## 🧱 Workflow Structure

**Webhook Node** → Listens for incoming `POST` requests from Postman

**Edit Fields Node** → Cleans and formats your input data

**Airtable Node** → Creates a new record in your Airtable table

---

## 🧩 How It Works

1. Postman sends a **POST request** to your n8n Webhook  URL.
2. n8n captures the JSON data.
3. The data passes through the **Edit Fields** node for formatting.
4. Airtable stores the clean record automatically.

---

## 💻 Testing With Postman

 **🟩 Step 1: Activate the Workflow**
In n8n, switch your workflow to **Active mode** and copy the production webhook URL (looks like `http://localhost:5678/webhook/submission`).

 **🟦 Step 2: Open Postman and Create a New Request**

1. Set the request type to **POST**.

2. Paste your webhook URL into the request URL field.

3. Go to the **Body** tab → select **raw** → choose **JSON**.

4. Enter this example data:
```json
{
  "name": "Velar-sudo",
  "email": "velar@example.com",
  "occupation": "Product Manager",
  "message": "Testing n8n webhook with Postman!"
}

```

 **🟨 Step 3: Send the Request**

- Click **Send** in Postman.
- You should see a success message from n8n like:
```json
{"message":"Workflow was started"}

```

 **🟧 Step 4: Verify Results**

- Open your **Airtable base** and check for the new record.
- You can also view the workflow execution in n8n under **Executions** → **List**.

---

## 🧠 Tips

- If Postman shows:
“When testing an API locally, you need to use the Postman Desktop Agent…”
→ Install the **Postman Desktop Agent** and restart Postman.

- Always use the **Production Webhook URL** for active workflows.

- If you move to a public server, replace `localhost` with your live domain or tunnel URL (e.g., from ngrok).

---

## 🏁 Summary

This version demonstrates how to simulate user form submissions using Postman instead of a browser.
It’s the best method to:

- Test automation flows before building a front-end.

- Validate Airtable data mappings.

- Debug webhook responses efficiently.

---

## 🔁 Improvements Over v2

- No need for an HTML form to test.

- Easier debugging and visualization of data flow.

- Simpler setup for backend testing and API validation.

---
🧩 Built with ❤️ by Velar-sudo using n8n

**Author**: Velar-sudo
**Version**: 3.0
**Workflow File**: `Form submission_postman_ver3.json`
**Created With**: n8n Local Instance (Linux Mint)
