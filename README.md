# Sleeping-Tracking
Sleeping Tracking with bangel js

Bangle.js AI Sleep Tracker

![alt text](https://via.placeholder.com/800x250.png?text=AI+Sleep+Tracker+for+Bangle.js)

A wearable system to monitor and analyze sleep patterns using a Bangle.js 1 smartwatch. This project leverages on-device sensors for data collection and a Python-based AI model for detailed sleep stage analysis and personalized recommendations.

🧠 Project Overview

This project turns a Bangle.js 1 into a powerful sleep monitoring tool. It continuously logs heart rate (HR) and accelerometer (movement) data throughout the night. This data is then processed by a classification model to identify sleep stages (Awake, Light, Deep, REM) and provide actionable insights to help improve the user's sleep quality.

The system is designed as a hybrid model to overcome the hardware constraints of the smartwatch:

On-Device Data Logging: A lightweight background service runs on the Bangle.js to efficiently collect sensor data.

PC-Based AI Analysis: A Python script uses a trained machine learning model (scikit-learn) to process the raw data, classify sleep stages, and generate personalized recommendations.

On-Device Visualization: The analysis results are uploaded back to the watch for easy viewing of sleep charts and summaries.

✨ Key Features

Manual Sleep Logging: Manually start and stop sleep tracking directly from the watch app for full control.

Sensor Data Collection: Logs heart rate and movement data every minute to a local sleepdata.json file.

AI-Powered Sleep Stage Detection: A Python script applies a trained classification model to identify four distinct sleep phases:

Awake: Periods of restlessness or being awake.

Light Sleep: The initial, lighter stages of sleep.

Deep Sleep: The most restorative stage of sleep.

REM Sleep: The stage associated with dreaming.

Personalized Recommendations: The analysis script provides simple, data-driven tips (e.g., "Aim for more deep sleep," "Reduce late-night movement").

Data Visualization: An intuitive on-watch interface displays:

A hypnogram (sleep stage chart) for the night.

Total sleep time and time in bed.

A breakdown of time spent in each sleep stage.

AI-generated recommendations.

(Optional) Instant On-Device Analysis: A "lite" version of the analysis can be run directly on the watch for a quick, convenient overview without needing a PC.

🛠️ Technical Stack

Hardware: Bangle.js 1

Firmware: JavaScript (Espruino)

Data Logging: Background service saving to local JSON storage.

AI Model & Analysis: Python 3, Pandas, Scikit-learn

Data Format:

Raw Data (sleepdata.json): [{"time": "...", "hr": 65, "movement": 1.01}, ...]

Analyzed Data (sleepdata.analyzed.json): Contains summary stats and a log of classified sleep stages.

🚀 Getting Started

Follow these steps to install and use the Sleep Tracker on your Bangle.js.

Prerequisites

A Bangle.js 1 Smartwatch

A computer with Python 3 installed

A web browser with Bluetooth support (e.g., Google Chrome)

The Bangle.js Web IDE

Installation

Clone the Repository:

Generated bash
git clone https://github.com/your-username/your-repo-name.git
cd your-repo-name


Install Python Dependencies:

Generated bash
pip install pandas scikit-learn
IGNORE_WHEN_COPYING_START
content_copy
download
Use code with caution.
Bash
IGNORE_WHEN_COPYING_END

Upload App to Bangle.js:

Connect your Bangle.js to the Web IDE.

In the left panel, click the Storage icon (looks like a floppy disk).

Click the "Upload a file" icon for each of the following files from the banglejs_code directory:

sleeplog.app.js

sleeplog.boot.js

sleeplog.metadata.json

In the Web IDE console, type reboot() and press Enter to restart the watch.

How to Use
Step 1: Track Your Sleep

On your Bangle.js, open the "Sleep Logger" app from the launcher.

The screen will show "IDLE". Press the main button (BTN1) to START logging. The watch will return to the clock face.

Wear the watch while you sleep.

When you wake up, open the "Sleep Logger" app again. It will show "LOGGING". Press BTN1 to STOP.

Step 2: Analyze Your Data

Connect the watch to the Web IDE.

Go to Storage and download the sleepdata.json file to the project folder on your computer.

Run the analysis script from your terminal:

Generated bash
python analyze_sleep.py
IGNORE_WHEN_COPYING_START
content_copy
download
Use code with caution.
Bash
IGNORE_WHEN_COPYING_END

This will create a new file named sleepdata.analyzed.json.

Step 3: View Your Results

In the Web IDE, upload the sleepdata.analyzed.json file back to your watch.

Open the "Sleep Logger" app. It will now display your detailed sleep stage chart and summary for the night!

📈 Project Status & Next Steps

✅ Data logging for heart rate and movement.

✅ Manual start/stop control from the watch.

✅ Working Python script for heuristic sleep phase classification.

✅ UI for displaying analyzed results.

⏳ Next Step: Improve the AI Model. Engineer more advanced features (e.g., heart rate variability) and train a more robust Random Forest or SVM model on labeled data.

⏳ Next Step: Implement On-Device Analysis. Port the heuristic model to JavaScript to provide users with an instant, "good enough" analysis directly on the watch.

⏳ Next Step: Enhance the UI. Add more interactivity and trend analysis (e.g., week-over-week sleep comparison).

🤝 Contributing

Contributions, issues, and feature requests are welcome! Feel free to check the issues page.

👥 Team

A: Hardware Integration & Sensor Setup

B: AI Model Training & Analysis

C: UI/UX Design & Data Presentation

📄 License

This project is licensed under the MIT License. See the LICENSE file for details.
