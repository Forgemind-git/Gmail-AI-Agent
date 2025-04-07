# Gmail AI Agent – n8n Workflow

This n8n workflow powers an AI email assistant that generates personalized email drafts using OpenAI and data from a Google Sheet. It is designed to automate email writing in various tones (formal, casual, friendly, etc.) based on the recipient's personality and name.

---

## 🔧 Features

- 📨 Triggered by a chat message (via LangChain Chat Trigger)
- 🤖 Uses GPT-4o Mini to generate custom email drafts
- 📋 Retrieves contact and tone information from Google Sheets
- 💬 Supports memory for contextual interactions
- ✉️ Prepares email drafts in Gmail (does **not** send automatically)

---

## 🧠 How It Works

1. **Trigger**: A chat message is received.
2. **Google Sheets Lookup**: Based on the recipient’s email ID, the system fetches:
   - Name
   - Personality (e.g., Formal, Friendly, Casual, Enthusiastic)
3. **AI Draft Generation**: The AI agent generates an email using:
   - The contact’s name
   - Personality tone
4. **Gmail Draft Creation**: A draft is prepared in Gmail without being sent.

---

## 🛠️ Nodes Used

- `When chat message received` – Trigger node
- `AI Agent` – LangChain agent orchestrating memory, tools, and logic
- `OpenAI Chat Model` – GPT-4o Mini for draft generation
- `Simple Memory` – Maintains conversational context
- `Google Sheets` – Retrieves contact information
- `Gmail` – Drafts email using AI-generated content

---

## 🔐 Credentials Needed

- `Google Sheets OAuth2`
- `Gmail OAuth2`
- `OpenAI API Key`

---

## 📎 Notes

- You can customize the prompt, model, and email subject easily.
- Make sure the Google Sheet includes `Name`, `Personality`, and `Mail IDs` columns.
- gpt-4o-mini model can be swapped for other providers supported by LangChain.

---

## 🎥 Created for [ForgeMindAI](https://youtube.com/@ForgeMindAI)

Feel free to remix this for custom AI agent workflows!
