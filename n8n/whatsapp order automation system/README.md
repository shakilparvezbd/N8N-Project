# 🤖 AI-Powered WhatsApp Sales & Order Automation Agent (n8n)

An advanced, 24/7 automated sales and order processing assistant built with **n8n**, integrating **WhatsApp**, **AI Models (Anthropic/OpenAI)**, and **Google Sheets**.

This workflow handles customer interactions seamlessly, processes multimedia inputs (text, voice, and images), qualifies leads, and automatically logs confirmed orders into Google Sheets without manual intervention.

---

## 🌟 Key Features

* **💬 24/7 Intelligent Chat:** Responds to customer inquiries instantly, answering questions about products, sizing, pricing, and availability in a natural, conversational tone (supports Bangla/Banglish/English).
* **🎙️ Multimodal Support:** Automatically handles and transcribes incoming voice notes and analyzes product images sent by customers.
* **🛒 Automated Order Collection:** Guides interested buyers through a structured ordering process and captures essential details (Name, Phone, Address, Product/Size).
* **📊 Real-time CRM Logging:** Uses a custom JavaScript parser to securely clean, validate, and append confirmed order data directly into **Google Sheets** with precise timestamps.
* **⚡ Instant Order Confirmation:** Triggers an automated confirmation message back to the customer on WhatsApp the moment their order is logged successfully.

---

## 🔄 Workflow Architecture

```text
[WhatsApp Trigger]
       │
       ├──> [Switch (Text / Image / Voice)]
       │         ├──> [Image Process / Vision AI]
       │         └──> [Voice Process / Whisper Audio Transcription]
       │
       ▼
[AI Agent (Anthropic/OpenAI + Memory + Knowledge Base)]
       │
       ▼
[If Node (Checks 'ORDER_READY:' Flag)]
       ├──> [False Branch] ──> [Normal Chat / WhatsApp Reply]
       └──> [True Branch]
                 │
                 ├──> [Code Node (JSON Parser & Cleaner)]
                 ├──> [Google Sheets (Append Order Row & Timestamp)]
                 └──> [WhatsApp (Success Confirmation Message)]
```

## 🛠️ Tech Stack & Tools

- **Orchestration:** n8n (Self-hosted or Cloud)
- **Messaging API:** Meta WhatsApp Cloud API
- **AI Engine:** Anthropic Claude / OpenAI GPT models
- **Database / CRM:** Google Sheets

## 🚀 Getting Started

1. **Import the workflow:** Download the workflow JSON file from this repository and import it into your n8n instance.
2. **Configure credentials:**
   - Set up your WhatsApp Trigger and Send Message nodes with your Meta Business API credentials.
   - Replace `YOUR_PHONE_NUMBER_ID` and `YOUR_RECIPIENT_PHONE_NUMBER` in the WhatsApp nodes with your own values.
   - Add your AI Chat Model API key (Anthropic/OpenAI).
   - Connect your Google Sheets account and replace `YOUR_GOOGLE_SHEET_ID` with your order tracking spreadsheet ID.
3. **Activate:** Toggle the workflow to Active and start testing via WhatsApp.
