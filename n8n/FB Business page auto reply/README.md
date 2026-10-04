# ⚽ AI Football Jersey Sales Agent (n8n Workflow)

An end-to-end automated Facebook Messenger AI Sales Agent built with **n8n**, **OpenRouter AI (LLM)**, **Groq (Speech-to-Text)**, **Vision AI**, and **Google Sheets**.

This workflow handles incoming messages from Facebook Messenger, processes multimodal input (Text, Image, and Voice Notes), checks stock availability from a Google Sheet Knowledge Base, and records completed customer bookings back to Google Sheets in JSON format.

---

## 🚀 Features

- 📩 **Multi-Modal Input Processing (Switch Router):**
  - **Text Messages:** Direct processing by AI Agent.
  - **Voice Notes (Audio):** Converted to text using **Groq Whisper API**.
  - **Images:** Analyzed using **Vision AI** to detect jersey details/photos.
- 🧠 **Smart Sales Conversational AI:**
  - Maintains conversation history using **Simple Memory**.
  - Trained to respond politely in English or Bengali script based on customer language.
  - Generates numbered stock lists (1, 2, 3...) dynamically.
- 📊 **Dynamic Knowledge Base (Google Sheets):**
  - Reads real-time product/stock data directly from Google Sheets.
- 📝 **Automated Booking & JSON Output:**
  - Extracts Name, Phone, Address, Thana, District, Size, and Team details upon booking.
  - Automatically appends/updates order data into Google Sheets.

---

## 🛠️ Tech Stack & Integration

- **Automation:** n8n Workflow
- **Messaging:** Facebook Messenger Graph API / Webhooks
- **LLM Engine:** OpenRouter AI Chat Model
- **Speech-to-Text:** Groq API (`whisper-large-v3`)
- **Database / KB:** Google Sheets API

---

## 📸 Workflow Architecture

*(Add screenshot of your n8n workflow here)*

---

## ⚙️ How to Import & Setup

1. **Import Workflow:**
   - Download the `fb-ai-auto-reply.json` file from this repository.
   - Open n8n, click on **Workflows** > **Import from file**, and upload the JSON.

2. **Configure Credentials:**
   - Set up your **Facebook App Webhook**.
   - Add your **OpenRouter API Key**.
   - Add your **Groq API Key** for voice transcription.
   - Connect your **Google Sheets OAuth2 / Service Account** for KB & Order Logging.

3. **Activate:**
   - Turn on the workflow toggle to **Publish**.