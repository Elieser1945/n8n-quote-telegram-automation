
# n8n Automated Quote Notification System 🚀

An automated workflow built with **n8n** (hosted via **Docker**) that periodically fetches random quotes from a REST API and pushes formatted real-time notifications to a **Telegram Bot**.

---

## 📌 Project Overview

This project demonstrates an end-to-end event-driven automation pipeline created using self-hosted **n8n**. It connects external REST APIs with instant messaging services using custom payload mapping and JSON data transformation.

---

## 🏗️ Architecture & Workflow

```
[ Manual / Schedule Trigger ] ──► [ HTTP Request Node ] ──► [ JSON Transformation ] ──► [ Telegram Bot API ]
```

1. **Trigger Node:** Initiates the workflow manually or via cron schedule.
2. **HTTP Request Node:** Fetches dynamic quote data from `https://dummyjson.com/quotes/random`.
3. **Payload Processing:** Parses and maps JSON response keys (`quote`, `author`) into formatted string expressions.
4. **Telegram Node:** Sends structured markdown/text messages to a specified Telegram Chat ID via Bot API.

---

## 🛠️ Tech Stack & Prerequisites

* **Orchestration / Automation:** [n8n](https://n8n.io/) (Self-Hosted)
* **Containerization:** Docker & Docker Desktop
* **API Integration:** REST API (GET request), Telegram Bot API
* **Data Format:** JSON / JavaScript Expressions

---

## 🚀 How to Run Locally

### 1. Start n8n Container
Run the following command in PowerShell / Terminal:

```bash
docker run -d \
  --name n8n \
  -p 5678:5678 \
  -v n8n_data:/home/node/.n8n \
  --restart always \
  docker.n8n.io/n8nio/n8n
```

Access the n8n dashboard in your browser at: `http://localhost:5678`

### 2. Import Workflow JSON
1. Open your n8n canvas.
2. Click on the top-left menu `...` -> **Import from File**.
3. Select the `quote-telegram-automation.json` file provided in this repository.

### 3. Configure Credentials
1. Create a Telegram Bot via `@BotFather` on Telegram and copy the API Access Token.
2. Update the **Telegram Node** credentials in n8n with your Bot Token.
3. Obtain your Chat ID via `@userinfobot` and paste it into the **Chat ID** field.
4. Click **Execute Workflow** to test!

---


## 📷 Screenshots / Demo

| n8n Workflow Canvas | Telegram Notification |
| :---: | :---: |
| ![n8n Workflow](assets/n8n-workflow.png) | ![Telegram Result](assets/telegram-result.png) |

> *Add your screenshot of the n8n canvas and Telegram chat result here!*

---

## 👤 Author
* **GitHub:** [@your-username](https://github.com/your-username)
* **LinkedIn:** [Your Name](https://linkedin.com/in/your-profile)
