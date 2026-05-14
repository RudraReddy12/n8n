# 🏥 AI-Powered Healthcare Automation Workflow

![n8n](https://img.shields.io/badge/n8n-Cloud-orange?style=for-the-badge&logo=n8n)
![OpenAI](https://img.shields.io/badge/OpenAI-GPT-412991?style=for-the-badge&logo=openai)
![Google Sheets](https://img.shields.io/badge/Google%20Sheets-API-34A853?style=for-the-badge&logo=googlesheets)
![Google Calendar](https://img.shields.io/badge/Google%20Calendar-API-4285F4?style=for-the-badge&logo=googlecalendar)
![Discord](https://img.shields.io/badge/Discord-Webhook-5865F2?style=for-the-badge&logo=discord)
![Status](https://img.shields.io/badge/Status-Published-brightgreen?style=for-the-badge)

---

## 📌 Overview

An end-to-end **healthcare automation pipeline** built on **n8n Cloud** that captures patient/health form submissions, processes them using an **AI-powered LLM Chain (OpenAI GPT)**, and intelligently routes outcomes — triggering real-time **Discord alerts** and auto-scheduling **Google Calendar events** based on AI-evaluated health data.

> ✅ Zero manual intervention | ✅ AI-driven decision-making | ✅ Multi-platform integration

---

## 🔄 Workflow Architecture

```
Form Submission
      │
      ▼
Append Row in Google Sheet
      │
      ▼
Edit Fields (Manual Mapping)
      │
      ▼
Basic LLM Chain ◄──── OpenAI Chat Model (GPT)
      │
      ▼
  IF Condition
  ┌───┴────┐
true      false
  │          │
  ▼          ▼
Google     Discord1
Calendar   (Alert)
(Event)
  │
  ▼
Discord
(Notification)
```

---

## ⚙️ Tech Stack

| Tool / Service        | Purpose                                      |
|-----------------------|----------------------------------------------|
| **n8n Cloud**         | Workflow automation platform                 |
| **OpenAI GPT**        | AI reasoning & LLM chain for health analysis |
| **Google Sheets API** | Patient data storage & record management     |
| **Google Calendar API**| Auto-scheduling health events/appointments  |
| **Discord Webhook**   | Real-time alerts & notifications             |
| **Basic LLM Chain**   | Structured prompt-response pipeline          |

---

## 🧩 Workflow Nodes — Step by Step

### 1. 📋 On Form Submission (Trigger)
- Listens for incoming healthcare form submissions
- Acts as the entry point of the entire pipeline
- Captures patient name, symptoms, date, and other health parameters

### 2. 📊 Append Row in Sheet
- Automatically appends each form submission as a new row in **Google Sheets**
- Maintains a structured, timestamped health data log
- Enables audit trail and data analytics

### 3. ✏️ Edit Fields (Manual Mapping)
- Formats and maps raw form fields into structured data
- Prepares the payload for the AI processing stage
- Handles field normalization and data cleaning

### 4. 🤖 Basic LLM Chain + OpenAI Chat Model
- Sends structured patient data to **OpenAI GPT** via a Basic LLM Chain
- AI evaluates health records and generates intelligent recommendations
- Returns a structured response used for downstream routing

### 5. 🔀 IF Condition (Decision Node)
- Evaluates the AI-generated output using conditional logic
- Routes the flow into two branches:
  - ✅ **True** → Schedules a Google Calendar event
  - ❌ **False** → Sends an alert via Discord

### 6. 📅 Create an Event (Google Calendar)
- Auto-creates a healthcare event (appointment/follow-up) in **Google Calendar**
- Triggered when the AI flags a critical/actionable health condition
- Includes relevant patient details in the event description

### 7. 💬 Discord / Discord1 (Notifications)
- Sends real-time messages to a **Discord channel** via Webhook
- Two Discord nodes handle different routing outcomes (true/false branches)
- Keeps healthcare teams instantly informed of patient status

---

## 🚀 How to Use

### Prerequisites
- [n8n Cloud account](https://n8n.io/)
- OpenAI API Key
- Google Cloud Project with Sheets & Calendar APIs enabled
- Discord Server with Webhook URL

### Setup Steps

1. **Clone / Import the Workflow**
   - Download the workflow JSON from this repo
   - Import it into your n8n Cloud instance via `+ New Workflow > Import`

2. **Configure Credentials**
   - Add your **OpenAI API Key** in n8n credentials
   - Connect **Google Sheets** and **Google Calendar** via OAuth2
   - Add **Discord Webhook URL** to the Discord nodes

3. **Set Up Google Sheet**
   - Create a Google Sheet with columns matching your form fields
   - Link the Sheet ID in the "Append Row in Sheet" node

4. **Activate & Publish**
   - Click `Publish` to make the workflow live
   - Test using the **Execute Workflow** button

---

## 📁 Project Structure

```
healthcare-n8n-automation/
│
├── workflow/
│   └── healthcare_workflow.json     # n8n workflow export
│
├── assets/
│   └── workflow_screenshot.png      # Workflow diagram
│
├── docs/
│   └── setup_guide.md               # Detailed setup instructions
│
└── README.md
```

---

## 📸 Workflow Screenshot

![Workflow](assets/workflow_screenshot.png)

---

## 🎯 Key Features

- 🔁 **Fully Automated** — Trigger-based, no manual steps required
- 🧠 **AI-Powered Analysis** — GPT evaluates health data intelligently
- 📊 **Data Persistence** — Every submission logged to Google Sheets
- 📅 **Smart Scheduling** — Auto-creates calendar events for follow-ups
- 🔔 **Instant Alerts** — Discord notifications for real-time awareness
- 🌿 **Scalable Architecture** — Easily extendable with new nodes/integrations

---

## 🔮 Future Enhancements

- [ ] Add **Twilio SMS** integration for patient alerts
- [ ] Connect **Slack** as an alternative to Discord
- [ ] Build a **dashboard** using Google Looker Studio on top of Sheets data
- [ ] Add **email notifications** via Gmail node
- [ ] Integrate **EHR (Electronic Health Records)** system APIs
- [ ] Add **error handling** and retry logic nodes

---

## 🧑‍💻 Author

**Your Name**
📧 your.email@example.com
🔗 [LinkedIn](https://linkedin.com/in/yourprofile) | [GitHub](https://github.com/yourusername)

---

## 📄 License

This project is licensed under the [MIT License](LICENSE).

---

> ⭐ If you found this project helpful, please give it a star!
