# GitHub Webhook Event Trigger Repository

This repository is used to generate GitHub webhook events such as:

- Push
- Pull Request creation
- Pull Request merge

These events are consumed by a separate webhook service that stores and displays repository activity.

---

## 🔄 Purpose

This repository acts as the **event source** for the webhook monitoring system.

It is connected to a webhook endpoint configured in:
Settings → Webhooks

The webhook endpoint forwards events to a Flask backend service via ngrok.

---

## 🚀 Events Tested

The following GitHub events are triggered from this repository:

### 1️⃣ Push Event
Triggered when:
- A commit is pushed to any branch.

### 2️⃣ Pull Request Event
Triggered when:
- A new pull request is opened.

### 3️⃣ Merge Event
Triggered when:
- A pull request is merged into the target branch.

---

## 🔗 Webhook Configuration

Webhook settings:

- **Payload URL:**  
  `https://<ngrok-url>/webhook/receiver`

- **Content Type:**  
  `application/json`

- **Events Selected:**  
  - Push  
  - Pull requests  

---

## 🧪 How to Test

### Test Push
1. Edit this README
2. Commit changes
3. Push to main

---

### Test Pull Request: 
1. Create a new branch
2. Push changes
3. Open a pull request

---

### Test Merge
1. Merge the pull request
2. Verify the merge event is received

---

## 📌 Notes

- The webhook endpoint must be publicly accessible (ngrok is used during development).
- Every time ngrok restarts, the webhook URL must be updated.
- This repository contains no backend logic — it only generates events.

---

## 🏗 Architecture Overview
action-repo
↓
GitHub Webhook
↓
ngrok public URL
↓
Flask Webhook Receiver
↓
MongoDB
↓
UI Dashboard

---

## 🛡️ Maintainer

Sneha Ilager  
