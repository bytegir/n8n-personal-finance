# n8n-personal-finance
***

```markdown
# 💰 Personal Finance Tracker & Chart Generator — n8n Workflow

A smart, autonomous personal finance automation system. Simply log your expenses via Telegram using everyday natural language, and the AI agent will automatically extract the data, update your balance, and generate visual financial charts.

## 📊 Workflow Architecture

```text
Telegram Trigger (Receives incoming messages)
    ↓
LLM Node / Groq (Extracts amount, item, & time)
    ↓
Data Processing (Calculates current balance)
    ↓
Chart Generation (Creates visual expense graphs)
    ↓
Save to Database/Sheet (Logs transaction history)
    ↓
Telegram Send (Delivers notifications & charts to user)
```

## ✨ Key Features

- **Natural Language Processing**: Log expenses effortlessly using conversational language (e.g., *"Bought a coffee for 25k"*).
- **Smart Time Recognition**: Highly accurate time conversion. If a user simply inputs "12" or "12 o'clock", the system is explicitly programmed to process it as 12:00 PM (noon) rather than defaulting to midnight, ensuring accurate daily tracking.
- **Automated Charting**: No more manual spreadsheets. The bot instantly generates and sends visual charts of your spending habits.
- **Real-time Balance Tracking**: Your financial balance is calculated and updated in real-time with every logged transaction.

## 🛠️ Prerequisites

Before importing this workflow, ensure you have set up the following accounts and credentials:

| Service / Node | Purpose | Free Tier? |
|---|---|---|
| **Telegram Bot API** | Receiving messages and sending text/image replies | ✅ Yes |
| **Groq / LLM** | Parsing conversational text into structured JSON data | ✅ Yes |
| **Google Sheets / DB**| Storing transaction history and balance calculations | ✅ Yes |
| **QuickChart API** *(Optional)* | Rendering visual charts from your data | ✅ Yes |

## 🚀 Quick Installation

### Step 1 — Import the workflow
1. Open your n8n canvas.
2. Click the **+** button in the top right corner, then select **Import from file**.
3. Upload the `personal-finance-bot.json` file from this repository.

### Step 2 — Configure Credentials
Open the **⚙️ Credentials** menu or configure them directly within the nodes:
1. **Telegram:** Go to BotFather on Telegram, create a new bot, and paste the API Token into the Telegram Trigger node.
2. **LLM (Groq):** Sign up for Groq (or your preferred LLM), generate an API Key, and add it to the AI/LLM node credentials.
3. **Database/Sheet:** Authenticate your Google account or database to grant n8n read/write access.

### Step 3 — Test & Activate
1. Run the workflow manually by clicking **Execute Workflow**.
2. Send a test message to your Telegram bot (e.g., *"Lunch chicken rice 15 thousand at 12"*).
3. If the nodes execute successfully and the bot replies with the correct balance and chart, click the **Active** toggle in the top right corner. You're all set! 🎉
