# 🏢 Secure Client Services Assessment Portal

Welcome to our official Client Services Assessment Portal. This repository hosts our secure, proctored evaluation environments for incoming candidates.

---

## 👤 For Candidates: What to Expect

If you have been directed here by our hiring team, congratulations on reaching the assessment phase of the interview process! 

This evaluation is designed to test your empathy, problem-solving, and communication skills in real-world scenarios. Please read the following guidelines carefully before using your provided **60-minute Access Code**.

### ⏱️ Assessment Format
* **Duration:** You will have exactly **60 minutes** to complete 20 scenarios.
* **Question Types:** You will encounter Multiple Choice, Written Emails, an Analytical Essay, and Audio Voicemail simulations.
* **Auto-Save:** Your progress is continuously saved to your browser. If your computer crashes, re-entering your Access Code will resume the exam right where you left off.

### 🔒 Strict Proctoring Rules
This is a secure testing environment. To ensure fairness for all candidates, the system enforces the following rules:
1. **Fullscreen Required:** The exam will automatically launch in fullscreen mode. **Do not exit fullscreen.**
2. **No Tab Switching:** If you switch tabs, open another window, or minimize the browser, a 10-second violation countdown will trigger. Failure to return immediately will result in an automatic forced submission.
3. **No Copy/Pasting:** The use of copy/paste (except for pasting your Access Code on the start screen) is strictly disabled.
4. **Microphone Access:** You will be prompted to allow microphone access. This is mandatory for the audio portions of the exam. Ensure you are in a quiet environment.

### 🔗 Assessment Links
Please select the link assigned to you by your recruiter:
* **[Junior / Entry-Level Assessment](https://[YOUR-USERNAME].github.io/[REPOSITORY-NAME]/junior/)**
* **[Senior / Advanced Assessment](https://[YOUR-USERNAME].github.io/[REPOSITORY-NAME]/senior/)**

*(Note: You must have a valid, unexpired Access Code to enter).*

---

## 🛠️ For Administrators: System Guide

This system is a decoupled web application. The frontend (UI and proctoring) is hosted here on GitHub Pages, while the backend (Database and File Storage) is powered securely by Google Apps Script and Google Workspace.

### 1. Generating Access Codes
Access codes are required for any candidate to begin an assessment. Codes expire 24 hours after generation and can only be used once.
* Open the **Assessment Database** Google Sheet.
* Click **Assessment Admin** in the top menu bar.
* Select **Generate 10 New Access Codes**.
* Distribute a code to the candidate along with the appropriate GitHub URL.
* *To manually revoke a code, change its status in the Sheet to `REVOKED`.*

### 2. Retrieving Results
When a candidate finishes their exam (or if they trigger a security violation), the system automatically compiles their data.
* **Google Sheet:** Logs the candidate's score, timestamps, and any security flags.
* **Google Drive Folder:** Automatically receives the candidate's `.webm` audio recordings (labeled by question type) and a cleanly formatted `.pdf` document containing all of their written responses.

### 3. Modifying the Assessment
To update questions, modify the Javascript arrays located directly within the `Code.gs` file in the Google Apps Script backend. You do not need to modify the HTML files in this repository to change question text. Remember to click **Deploy > New Deployment** in Google Apps Script after making any changes.
