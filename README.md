# Reply Craft – AI Email Writer Chrome Extension

Reply Craft is an AI-powered Chrome extension that helps users generate professional, clear, and context-aware email replies directly inside Gmail. It uses the Gemini AI API through a Spring Boot backend to create context-aware responses you can insert into Gmail.

---

## Table of Contents
- [Features](#-features)
- [Tech Stack](#-tech-stack)
- [Architecture Overview](#-architecture-overview)
- [Installation](#-installation)
  - [Clone the repository](#-step-1-clone-the-repository)
  - [Setup Backend (Spring Boot)](#-step-2-setup-backend-spring-boot)
  - [Load Chrome Extension](#-step-3-load-chrome-extension)
- [How to Use](#-how-to-use)
- [Project Structure](#-project-structure)
- [Permissions Used](#-permissions-used)
- [Security Notes](#-security-notes)
- [Future Enhancements](#-future-enhancements)
- [Contributing](#-contributing)
- [License](#-license)
- [Acknowledgments](#-acknowledgments)

---

## 🚀 Features
- Generate AI-based email replies inside Gmail
- One-click reply generation
- Context-aware responses using Gemini AI
- Improves productivity and email quality
- Clean and simple user interface
- Secure backend API using Spring Boot

---

## 🛠 Tech Stack

### Frontend (Chrome Extension)
- HTML, CSS, JavaScript
- Chrome Extension APIs

### Backend
- Java
- Spring Boot (REST API)

### AI Integration
- Google Gemini API

---

## ⚙ Architecture Overview
```bash
Chrome Extension (UI)
        |
        |  HTTP Request (Email Content)
        ▼
Spring Boot Backend (REST API)
        |
        |  Request to Gemini API
        ▼
     Gemini AI
        |
        ▼
Generated Reply → Back to Extension → Insert into Gmail
```

---

## 📥 Installation

### 🔹 Step 1: Clone the Repository
Clone your repository locally (example using this repo):
```bash
git clone https://github.com/madhabendra-baral/GitDemo3.git
cd GitDemo3
```

> If you fork or move this project, replace the URL above with your repository URL.

---

### 🔹 Step 2: Setup Backend (Spring Boot)

1. Open the backend project in your IDE (IntelliJ / Eclipse / VS Code).
2. Configure the Gemini API key. Recommended: use an environment variable to avoid committing secrets.

Example using `application.properties` with environment variable substitution:
```properties
# application.properties
gemini.api.key=${GEMINI_API_KEY:}
```

Set the environment variable (example for macOS / Linux):
```bash
export GEMINI_API_KEY="your_real_gemini_api_key_here"
```

3. Run the Spring Boot application:
```bash
mvn spring-boot:run
```

Backend will start on:
```text
http://localhost:8080
```

If you need a different port, change `server.port` in `application.properties`.

---

### 🔹 Step 3: Load Chrome Extension

1. Open Chrome and go to:
```text
chrome://extensions/
```
2. Enable **Developer Mode** (top-right).
3. Click **Load unpacked**.
4. Select the **extension (frontend) folder** (e.g., `extension/` in this repo).

✅ Reply Craft should now be installed in your browser.

---

## 📧 How to Use

1. Open **Gmail** in Google Chrome.
2. Open any email you want to reply to.
3. Click the **“Reply Craft” / “AI Reply”** button added by the extension.
4. The extension sends the email content to your Spring Boot backend.
5. Backend requests the **Gemini API** and returns a generated reply.
6. The reply is inserted into the Gmail compose box.
7. Edit if needed and click **Send**.

---

## 📂 Project Structure
```bash
reply-craft/
│
├── backend/                 # Spring Boot API
│   ├── src/main/java/...
│   ├── src/main/resources/application.properties
│   └── pom.xml
│
├── extension/               # Chrome Extension (Frontend)
│   ├── manifest.json
│   ├── content.js
│   ├── popup.html
│   ├── popup.js
│   ├── styles.css
│   └── icons/
│
└── README.md
```

---

## 🔐 Permissions Used
- `activeTab`
- `storage`
- `scripting`
- `https://mail.google.com/*`

These permissions are required to integrate with Gmail and manage user interactions.

---

## 🔒 Security Notes
- Never commit API keys or secrets to the repository.
- Use environment variables or a secrets manager for the Gemini API key.
- Consider adding server-side rate limiting and authentication if you plan to share the backend.
- Use HTTPS in production for both the backend and any external calls.

---

## 🧠 Future Enhancements
- Multiple tone options (Formal, Friendly, Follow-up, Apology)
- Email summarization
- Multilingual support
- Custom templates
- User authentication
- Dark mode UI

---

## 🤝 Contributing

Contributions are welcome! Suggested workflow:
1. Fork the repository  
2. Create a feature branch:
```bash
git checkout -b feature/your-feature-name
```
3. Commit your changes:
```bash
git commit -m "Add: short description of change"
```
4. Push to your branch:
```bash
git push origin feature/your-feature-name
```
5. Open a Pull Request describing what you changed and why.

---

## 📄 License
This project is currently developed for educational and personal use. Consider adding a license (e.g., MIT) if you want to allow others to reuse it.

---

## ⭐ Acknowledgments
- Google Gemini API  
- Spring Boot Framework  
- Chrome Extension Documentation

---

## ✅ Notes for You
- Replace clone URL above if you move this README to a different repository.
- Ensure `GEMINI_API_KEY` is set in your environment before running the backend.
