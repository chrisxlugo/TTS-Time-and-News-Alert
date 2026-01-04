Trading Dashboard — Timers + News + Economic Calendar

This project is a custom intraday trading dashboard that displays:

✅ synchronized candlestick countdown timers
✅ market session countdown
✅ Yahoo Finance news
✅ Forex Factory economic calendar (current week)
✅ optional Text-to-Speech alerts

⚠️ Note: This project was built with the assistance of AI as a development tool.

🧩 Requirements
1️⃣ Install Node.js

Download from:

https://nodejs.org

Verify install in terminal / command prompt:

node -v

2️⃣ Install Node dependencies

In the project folder run:

npm init -y
npm install express cors


(No other dependencies are required.)

📁 Folder Structure

Example:

TradingDashboard/
 ├─ main.html
 ├─ server.js
 ├─ start-dashboard.bat   (optional launcher for Windows)
 └─ README.md

🖥️ How It Works (Simple Overview)

The HTML dashboard (main.html) runs in your browser

A small Node.js backend (server.js):

fetches economic calendar JSON from Forex Factory

filters by date / country / impact

serves data to the dashboard locally at:

http://localhost:3000/api/ff-calendar


This setup avoids CORS and scraping issues

Forex Factory JSON supports:

current week

previous week

(future weeks when published)

This dashboard is designed for intraday use — so as long as the event is in the current week, it will appear.

🚀 Running The Dashboard
Method 1 — Manual Start (Developer-Style)
Start backend

Open a terminal in the project folder:

node server.js


You should see:

FF calendar backend running at http://localhost:3000

Open the dashboard

Double-click:

main.html


(or open in Brave / Chrome)

📌 Now the economic calendar + news + timers will load.

Method 2 — One-Click Launcher (Recommended on Windows)

Create a file named:

start-dashboard.bat


Paste:

@echo off
cd /d "%~dp0"

start "EconServer" cmd /c "node server.js"

timeout /t 2 >nul

start "" "C:\Program Files\BraveSoftware\Brave-Browser\Application\brave.exe" "file:///%~dp0main.html"


(Adjust browser path if needed)

Now just double-click the .bat file 🎯

📡 Economic Calendar Notes

Data source:

https://nfs.faireconomy.media/


Supported files:

ff_calendar_thisweek.json

ff_calendar_lastweek.json

ff_calendar_nextweek.json (only when published)

Intraday behavior (intended use case)

✔ Monday shows Monday events
✔ Any day shows current week
✔ Last week view works
⚠️ Next week works only when FF publishes JSON

This is fine for intraday trading
(long-term prep still best done on FF website)

🔊 TTS (Optional)

Enable or disable in the dashboard UI.

Used for:

candle closes

news alerts

econ alerts (if supported)

🎨 UI Summary

Includes:

✔ dark terminal-style theme
✔ configurable timers
✔ mute per timeframe
✔ session countdown
✔ news panel
✔ econ calendar widget
✔ customizable settings

⚠️ Disclaimer

This dashboard is:

for educational & personal trading workflow use only

not investment advice

not affiliated with Forex Factory or Yahoo Finance

All data belongs to respective providers.

🤖 About AI Usage

This project was built with AI assistance as a development tool.
The final implementation was reviewed and adapted manually.
