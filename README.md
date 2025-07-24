# 📺 YouTube Title & Description Auto Generator (with Google Sheets & Email Integration) using n8n

<img width="1172" height="493" alt="Screenshot 2025-07-24 at 10 04 31 AM" src="https://github.com/user-attachments/assets/b291e088-f51d-4cdd-b702-b0b4b33a0ad2" />

## 🔧 Overview

This project automates the process of:
- Fetching YouTube video links from a Google Sheet
- Extracting transcripts using a YouTube transcript service
- Generating engaging **titles** and **descriptions** using Google Gemini Chat (via LLM)
- Sending the generated content to your email
- Updating the original Google Sheet with the final output

Built entirely using [n8n](https://n8n.io), this workflow streamlines YouTube SEO operations for content creators and marketing teams.

---

## ✨ Features

- 🧠 AI-generated YouTube titles & descriptions using **Gemini Chat**
- 📥 Integration with **Google Sheets** for data input & update
- 📬 Sends email with generated results
- 🔄 Fully automated via **Scheduled Trigger**
- 🔗 Transcript fetched from YouTube using public transcript API

---

## 🔄 Workflow Structure

1. **Schedule Trigger**: Automatically runs the workflow at a specified time.
2. **Get row(s) in sheet**: Reads rows from a connected Google Sheet (containing YouTube video links).
3. **Loop Over Items**: Iterates over each row to process individual videos.
4. **Extract Link**: Extracts and cleans the YouTube link if needed.
5. **Code**: Parses video ID from the URL.
6. **Get Transcripts**: Calls a public API to fetch YouTube transcripts.
7. **Extract Transcripts**: Extracts raw transcript content from the response.
8. **Combine Transcripts**: Merges the transcript into a single block of text.
9. **Basic LLM Chain**: Prepares a prompt for the AI model.
10. **Google Gemini Chat**: Sends the transcript to Gemini for title & description generation.
11. **AI Agent (Optional)**: Further refines or enhances the content.
12. **Send a Message**: Sends an email to the user with the generated YouTube title & description.
13. **Update Row in Sheet**: Updates the Google Sheet with the generated output.

---

## 📂 Input Format (Google Sheet)

Your Google Sheet should have at least the following columns:

| Video Link | Title | Description |
|------------|-------|-------------|
| https://www.youtube.com/watch?v=xxxxxx | *(auto-filled)* | *(auto-filled)* |

The workflow reads the `Video Link` column, processes it, and updates the `Title` and `Description` columns.

---

## 📧 Output Format (Email)

The email sent will contain:

```

Subject: YouTube Title & Description for \[Video Title or ID]

Body:
✅ **Title**: \[Generated Title]

📝 **Description**:
\[Generated Description]

````

---

## 📸 Screenshot

You can see the entire n8n visual workflow below:

<img width="1172" height="493" alt="Screenshot 2025-07-24 at 10 04 31 AM" src="https://github.com/user-attachments/assets/0e99f6f5-d782-4f86-ba72-4d1d677043bd" />

---

## 📦 Prerequisites

- n8n (self-hosted or cloud)
- Google account with access to Google Sheets
- YouTube transcript API or self-hosted extractor
- Gmail credentials set up in n8n
- Google Gemini API credentials or plugin for n8n

---

## 🔑 Configuration

1. **Google Sheets**
   - Set up OAuth2 credentials in n8n for Google Sheets.
   - Use “Get row(s)” and “Update row” nodes to fetch and write data.

2. **YouTube Transcript API**
   - Add a `HTTP Request` node to get transcripts using the `videoId`.

3. **LLM / Gemini**
   - Integrate Gemini API or use a third-party plugin in n8n to generate titles & descriptions.

4. **Email**
   - Set up the `Send Email` node (Gmail or SMTP).

---

## 💻 Installation

Clone the repository:

```bash
git clone https://github.com/umeshyadav7988/youtube-auto-description-generator.git
cd youtube-auto-description-generator
````

> Import the workflow JSON into your local or cloud n8n instance.

---

## 📬 Contact

* **GitHub**: [umeshyadav7988](https://github.com/umeshyadav7988)
* **Email**: [umeshyadav7988@gmail.com](mailto:umeshyadav7988@gmail.com)

---




