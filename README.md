# webhook-repo

# GitHub Webhook Activity Tracker

This project captures GitHub repository events using webhooks, stores them in MongoDB, and displays recent activity in a simple Angular UI.

---

## 📂 Repositories

### 1. action-repo
Used to trigger GitHub events such as:
- Push
- Pull Request

### 2. webhook-repo
Contains:
- Flask backend (webhook receiver)
- MongoDB integration
- Angular frontend (activity feed)

---

## ⚙️ Tech Stack

- Backend: Flask (Python)
- Database: MongoDB
- Frontend: Angular
- Integration: GitHub Webhooks
- Tunneling: ngrok

---

## 🔄 Application Flow

1. GitHub repository action occurs (Push / PR)
2. GitHub sends webhook event
3. Flask API receives webhook
4. Required data is stored in MongoDB
5. Angular UI polls backend every 15 seconds
6. Latest activity is displayed on UI

---

## 🗄️ MongoDB Schema

```json
{
  "request_id": "string",
  "author": "string",
  "action": "PUSH | PULL_REQUEST | MERGE",
  "from_branch": "string | null",
  "to_branch": "string",
  "timestamp": "string"
}
