# **TABLE‑BOOKING‑BOT**

```
# -----------------------------------------
# n8n Project – Git Ignore Configuration
# -----------------------------------------

# Prevent exported credentials from ever being committed
.credentials

# Environment variables (API keys, secrets)
.env

# Node dependencies (if you ever add custom nodes or scripts)
node_modules/

# VS Code workspace settings
.vscode/

# macOS system files
.DS_Store

# Temporary files
*.log
*.tmp
*.swp

# OS-specific trash folders
Thumbs.db
```

This keeps your repo clean and ensures **no sensitive data** ever ends up on GitHub.

---

# **Setup Instructions (Add to Your README)**  
Here is a polished, ready‑to‑paste section for your README that explains how to safely reconnect credentials when someone imports your workflow.

---

## Setup Instructions: Connecting Your Own Credentials

This project does **not** include any API keys or credentials. For security reasons, all sensitive information is stored locally inside n8n and is never committed to GitHub.

To run this workflow on your own n8n instance, follow these steps:

### **1. Import the Workflow**
1. Open n8n  
2. Go to **Workflows → Import**  
3. Select `table-booking-bot.json` from the `workflows/` folder  

n8n will import the workflow **without credentials**, which is expected.

---

### **2. Reconnect the Google Gemini API**
1. Open the **Google Gemini Chat Model** node  
2. Under **Credentials**, click **Reconnect** or **Create New**  
3. Add your own Gemini API key  
4. Save the node  

---

### **3. Reconnect Google Sheets**
Both the **Read Bookings Tool** and **Add Booking Tool** require Google Sheets access.

1. Open each Google Sheets Tool node  
2. Under **Credentials**, click **Reconnect** or **Create New**  
3. Authenticate with your Google account  
4. Save the node  

---

### **4. Create Your Own Google Sheet**
The workflow expects a sheet with the following columns:

- Name  
- Date  
- Time  
- Number of People  

You can use any spreadsheet ID — just update the **documentId** and **sheetName** fields in the nodes.

---

### **5. Publish the Workflow**
Once credentials are connected:

1. Click **Activate**  
2. Enable **Chat** mode if using the n8n chat widget  
3. Your booking bot is ready to use  

---

### **Why Credentials Are Not Included**
- API keys must never be shared publicly  
- n8n stores credentials securely and separately from workflow JSON  
- The `.gitignore` file prevents accidental commits of sensitive files  

---

