# 🤖 AI-Powered User Analysis & Vehicle Suggestion System (n8n + Google Sheets)

An intelligent automation workflow built using **n8n** that collects user data, analyzes it, stores it in **Google Sheets**, and uses **AI (Google Gemini)** to suggest a suitable vehicle based on user profile — all fully automated with email delivery.

---

## 🚀 Features

- 📝 User data collection via form (Name, Age, Gender, Email)
- 📊 Automatic data storage in Google Sheets
- 🔀 Conditional logic using Switch node
- 🧾 Dynamic remark generation based on age
- 🌐 External API integration (via JavaScript Code node)
- 🧠 AI-powered vehicle suggestion
- 📧 Automated email notification
- ⚡ Fully automated end-to-end workflow

---

## 🛠 Tech Stack

- **n8n** – Workflow automation  
- **Google Sheets API** – Data storage & updates  
- **Google Gemini AI** – Intelligent recommendations  
- **JavaScript (Code Node)** – API integration  
- **Gmail API** – Email notifications  

---

## 🔄 Workflow Overview

1. User submits form with details  
2. Data is stored in Google Sheets  
3. Switch node categorizes user based on age:
   - Below 18  
   - 18–60  
   - Above 60  
4. Remark is updated in sheet:
   - 🚫 Below 18 → *"You cannot drive"*  
   - ✅ 18–60 → *"You are eligible for a licence"*  
   - ⚠️ Above 60 → *"It's risky for you to drive"*  
5. External API is called via JavaScript node  
6. AI Agent generates a vehicle suggestion:
   - Bicycle (if under 18)  
   - Car/Bike based on personality  
7. Suggestion is stored in Google Sheets  
8. Email is sent to the user with recommendation  

---

## 🧩 Nodes Used

- **Form Trigger** → Collects user data  
- **Google Sheets (Append)** → Stores new entry  
- **Switch Node** → Age-based logic  
- **Google Sheets (Update)** → Adds remarks  
- **Code Node (JavaScript)** → API call  
- **AI Agent (LangChain)** → Generates suggestion  
- **Google Gemini Chat Model** → AI processing  
- **Google Sheets (Update)** → Stores suggestion  
- **Gmail Node** → Sends email  

---

## 📊 Google Sheet Structure

| Name | Age | Gender | Email | Remark | Suggest |
|------|-----|--------|-------|--------|--------|

---

## ⚙️ Setup Instructions

### 1️⃣ Import Workflow
- Open n8n  
- Import the provided JSON file  

---

### 2️⃣ Configure Credentials

- Connect **Google Sheets account**
- Add **Google Gemini API**
- Connect **Gmail OAuth2**

---

### 3️⃣ Run Workflow

- Activate workflow  
- Open form URL  
- Fill user details  
- Receive suggestion via email 📩  

---

## 🧠 AI Logic

- If **Below 18** → Suggests *Bicycle*  
- If **18–60 / Above 60** → Suggests:
  - Car 🚗  
  - Bike 🏍  
  - Based on personality inputs  

---

## 🌐 API Integration

The workflow includes a **Code Node** that fetches data from an external API:

```js
const data = await this.helpers.httpRequest({
  method: "GET",
  url: "https://jsonplaceholder.typicode.com/posts/1"
});
``` id="h2k9dn"

---


