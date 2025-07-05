Bangle.js AI Sleep Tracker & Web Analyzer
A complete ecosystem for sleep monitoring using a Bangle.js 1 and final state of your project. It explains the "why" behind the final design choices (like using a command-based model smartwatch. This project features a robust on-watch application for data collection and a modern web application for fetching, analyzing, and instead of auto-send), which is excellent for showing your understanding in a project portfolio.
This README is designed to be visualizing sleep data over Bluetooth.
This repository contains all the code needed to build:
A B a complete guide for anyone, including your future self or a project assessor, to understand, install, and use your entireangle.js App: A simple, efficient app to start and stop sleep logging (Heart Rate & Movement).
A Web Application: A single index.html file that connects to the watch, fetches the data, performs ecosystem (Bangle.js app, Android app, and Web App).
*README.md sleep stage analysis, and displays a beautiful, interactive report.
🚀 Features

# Bangle.js AI Sleep Tracker & Analysis Suite

 <!-- It's a good idea to create a simple banner image On-Watch Control:** Simple, full-screen UI on the Bangle.js to START and STOP sleep tracking.
*   **📡 Bluetooth Data Transfer:** A dedicated "Send Data" mode on the watch makes it discoverable by the web app. -->

**A complete, end-to-end wearable system to monitor, fetch, and analyze sleep patterns. This project uses a Bangle.js 1 smartwatch for data collection and provides both a native Android app and a browser-based Web App for sophisticated
*   **🌐 Universal Web Analyzer:** A single HTML file that runs in any Web Bluetooth-compatible browser (like Google Chrome) to fetch and analyze data. No installation required.
*   **🧠 Instant Sleep Analysis:** The web app re analysis and visualization.**

This project has evolved through multiple stages of debugging and refinement to create a robust and user-friendly experience, demonstrating key principles of embedded systems and mobile application development.

---

## 🚀 The Ecosystem

This project consists of three-implements the sleep analysis logic in JavaScript to instantly classify sleep stages:
    *   **Awake:** Periods of restlessness distinct, cooperative parts:

1.  **Bangle.js App (`Sleep Tracker`):** A power-efficient app.
    *   **Light Sleep:** The majority of sleep.
    *   **Deep Sleep:** The most restorative stage. with a simple UI to start/stop sleep logging. It also features a dedicated "Send Mode" to prepare the watch for data
    *   **REM Sleep:** The dreaming stage.
*   **📊 Rich Visualization:** Uses `Chart.js` transfer.
2.  **Android App:** A native Kotlin app that connects to the Bangle.js, fetches the raw to display a professional hypnogram (sleep stage chart) with a heart rate graph overlay.
*   **💡 sleep data, performs on-device analysis, and displays a beautiful, easy-to-read sleep report and chart.
3. Actionable Insights:** Provides a clean "Sleep Report" card with total sleep time, time in each stage, and a personalized recommendation.  **Web-Based Analyzer (`index.html`):** A zero-installation web page that uses the Web Bluetooth API to

---

## 🛠️ How it Works: The Architecture

The system uses a stable, command-based architecture to avoid crashes and ensure reliable data transfer.

1.  **Logging:** The `sleeptracker.boot.js` script perform the same function as the Android app, offering a universal solution for desktop users.

---

## ✨ Key Features

*   **Robust Data Logging:** A background service on the Bangle.js collects Heart Rate (HR) and Movement data runs in the background on the Bangle.js. When activated by the `sleeptracker.app.js`, it logs HR and movement to a `sleeptracker.data.json` file.
2.  **Advertising:** When the user once per minute, filtering for high-confidence readings.
*   **Simple On-Watch Control:** A clear, full-screen enters "Send Data" mode in the app, the watch starts advertising the Nordic UART service, making it visible to the web UI lets users Start/Stop logging and enter a dedicated "Send Data" mode with explicit button controls (BTN1, BTN app.
3.  **Connection:** The web app (`index.html`) scans for and connects to the watch.
4.  **Command:** The web app sends a lightweight command (`\x10loadsleep\n`)2, BTN3).
*   **Command-Based Data Transfer:** Uses a stable, command-based protocol. The client app (Android/Web) connects and sends a command, and the watch responds with the data. This to the watch.
5.  **Response:** The `boot.js` script receives the command, reads the JSON proven method avoids the race conditions and crashes that can occur with "auto-send" designs.
*   **On file from storage, and sends its contents back in small, safe chunks over Bluetooth.
6.  **Analysis & Display:** The web app receives all the chunks, reassembles the file, performs the analysis, and displays the report and-the-Fly Analysis:** Both the Android and Web apps contain a JavaScript/Kotlin port of the sleep analysis algorithm. They chart.

---

## 📖 Getting Started: A Step-by-Step Guide

### Step 1: Set process the raw data instantly to classify sleep stages:
    *   **Awake:** Periods of restlessness.
    *   **Light Sleep:** Lighter stages of sleep.
    *   **Deep Sleep:** The most restorative stage.
 Up Your Bangle.js

First, you need to install the application on your watch.

1.  **Connect    *   **REM Sleep:** The stage associated with dreaming.
*   **Rich Visualization:** Displays a professional " to the Bangle.js Web IDE.**
2.  In the Storage view, delete any old `sleeptrSleep Report Card" with key metrics and a `Chart.js`-powered hypnogram that overlays the heart rate data for a comprehensive view.
*   **Simulation Mode (Android):** The Android app includes a built-in "acker` or `sleeplogger` files to ensure a clean slate.
3.  Upload the two files below:

    *   **`sleeptracker.app.js` (The App UI):**
        Simulate & Analyze" mode with embedded sample data, allowing for UI development and demonstration without a live connection to the watch.

---

## 🛠️ Technical Stack

*   **Hardware:** Bangle.js 1
*   **Watch```javascript
        // File: sleeptracker.app.js
        const SETTINGS_FILE = 'sleeptracker.settings.json';
        const DATA_FILE = 'sleeptracker.data.json';

        function drawMainUI() {
          let settings = require("Storage").readJSON(SETTINGS_FILE, true) || {};
 Firmware:** JavaScript (Espruino)
*   **Android App:** Kotlin, MPAndroidChart Library
*   **Web App:** HTML, CSS, JavaScript, Web Bluetooth API, Chart.js Library
*   **Communication Protocol:** Bluetooth Low Energy (BLE) using the Nordic UART Service.

---

## 🔧 Installation & Usage

### 1. Bangle          let isLogging = settings.isLogging || false;
          g.clear(); Bangle.loadWidgets(); Bangle.drawWidgets(); g.setFontAlign(0, 0);
          if (isLogging) {
            g.setFont("Vector", 40).setColor("#ff0000").drawString("LOGGING", g.getWidth()/2, g.getHeight()/2 - 30);
            g.setFont("6x8", 2).setColor.js Setup

1.  **Perform a Clean Install:** It is highly recommended to start with a clean watch. Connect to the [Bangle.js Web IDE](https://www.espruino.com/ide/), run `reset()(g.theme.fg).drawString("Press BTN1 to STOP", g.getWidth()/2, g.getHeight()/2 + 30);
          } else {
            g.setFont("Vector", 40).setColor("#00ff00").drawString("IDLE", g.getWidth()/2, g.getHeight()/2 - 30);
            g.setFont("6x8", 2).setColor(g.theme`, then `Storage.eraseAll()` to wipe the watch's storage.
2.  **Upload App Files:** From the `/banglejs_code` directory of this repository, upload the following files to your watch's storage using the Web IDE:
    *   `sleeptracker.app.js`
    *   `sleeptracker.boot.js`
3.  **Reboot:** In the Web IDE console, type `reboot()` and press Enter..fg).drawString("Press BTN1 to START", g.getWidth()/2, g.getHeight()/2 + 30);
          }
          g.setFont("6x8", 2).setColor(g.theme.fg).drawString("BTN3: Send | BTN2: Exit", g.getWidth()/2, g

### 2. Usage Workflow

1.  **Track Sleep:**
    *   On your Bangle.js, open the **"Sleep Tracker"** app.
    *   Press **BTN1** to **START** logging. The app will confirm and exit to the clock face.
    *   When you wake up, open the app.getHeight() - 20);
        }

        function showSendDataScreen() {
          g.clear();
          g.setFont("Vector", 20).setFontAlign(0, 0).drawString("Ready to Send", g.getWidth()/2, g.getHeight()/2 - 40);
          g.setFont("6x8", 2).setFontAlign(0,0).drawString("Open Web or Android app\nand press 'Connect'.", g.getWidth()/2, g.getHeight()/2);
          g.setFont(" again and press **BTN1** to **STOP**.

2.  **Analyze Data (Web App Method):**
    *   Open `index.html` in a compatible browser (Google Chrome is recommended).
    *   On your6x8", 1).drawString("Press any button to go back.", g.getWidth()/2, g.getHeight() - 10);
          NRF.setAdvertising({}, { showName: true, uart: true });
          clearWatch();
          const goBack = () => { NRF.setAdvertising({}); setupMainScreen(); };
          setWatch(goBack, BTN1, { edge: "falling" });
          setWatch( watch, open the "Sleep Tracker" app and press **BTN3** to enter "Ready to Send" mode.
    *   On the webpage, click **"Connect & Analyze Sleep Data"** and select your Bangle.js from the pop-up.
    *   The data will be fetched, analyzed, and displayed.

3.  **Analyze DatagoBack, BTN2, { edge: "falling" });
          setWatch(goBack, BTN3, { edge: "falling" });
        }

        function setupMainScreen() {
          drawMainUI();
          setWatch(() => {
            let settings = require("Storage").readJSON(SETTINGS_FILE, true) || {};
            if (settings.isLogging) {
              require("Storage").writeJSON( (Android App Method):**
    *   Install and run the Android app.
    *   On your watch, open the "Sleep Tracker" app and press **BTN3** to enter "Ready to Send" mode.
    *   In the Android app, tap **"Fetch Sleep Data from Bangle.js"**.
    *   The data will be fetched, analyzed, and displayed.

---

## 🎓 Project Learnings & Design Choices

A significantSETTINGS_FILE, { isLogging: false });
              E.showMessage("Logging Stopped", "Sleep Tracker");
              setTimeout(drawMainUI, 500); 
            } else {
              require("Storage").erase(DATA_FILE);
              require("Storage").writeJSON(SETTINGS_FILE, { isLogging: true });
              E.showMessage("Logging Started...", "Sleep Tracker");
              setTimeout(load, 1000); 
            }
          }, BTN1, { edge: "falling", repeat: true });
          setWatch part of this project involved debugging real-world embedded systems challenges. The final architecture was chosen for maximum stability.

*   **Command-Based vs. Auto-Send:** An initial "auto-send on connect" design was tested but proved unstable, causing the Bangle.js Bluetooth stack to crash due to a race condition between the `connect` event and a(() => { clearWatch(); load(); }, BTN2, { edge: "falling", repeat: true });
          setWatch(showSendDataScreen, BTN3, { edge: "falling", repeat: true });
        }
        setupMainScreen();
        ```

    *   **`sleeptracker.boot.js` (The Background Service):**
        ```javascript
        // File: sleeptracker.boot.js
        (function() {
          const STORAGE_FILE = 'sleeptracker.data.json';
          const SETTINGS_FILE = 'sleeptracker.settings.json';
          const LOG_INTERVAL_MS = 60000; "heavy" file-reading operation. The final implementation uses a more robust command-based model (`\x10loadsleep`), which is the industry standard for this type of communication.
*   **Firmware & Cache Issues:** The development process revealed issues caused by conflicting boot scripts, stale IDE connections, and corrupted build caches, highlighting the importance of a clean development and testing environment (e.g., using `reset()`, `Storage.eraseAll()`, and "Invalidate C

          let logInterval, dataBuffer = [], isCurrentlyLogging = false;
          let lastMovement = {x:0,y:0,z:0}, currentMovement = 0, lastHR = 0;
          Bangle.on('HRM', hrm => { if (hrm.confidence > 80) lastHR = hrm.bpm; });
          Bangle.on('accel', acc => { let m=Math.abs(acc.x-lastMovement.x)+Math.abs(acc.y-lastMovement.y)+Math.abs(acc.z-lastMovement.z); currentMovement += m; lastMovement = acc; });
          function logData() { if (lastHR > 0) { dataBuffer.push({ "time": new Dateaches and Restart").
*   **Simulation-First Development:** When faced with hardware or connectivity issues, development shifted to a "simulation" model in the Android app. This allowed for rapid UI/UX development and refinement of the analysis logic in isolation, a key strategy for complex projects.

This project serves as a comprehensive case study in building a complete IoT ecosystem, from the low-level firmware on a constrained device to high-level data visualization in web and mobile applications.
