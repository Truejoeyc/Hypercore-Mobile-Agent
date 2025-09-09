# Hypercore-Mobile-Agent
Nexus Assistant is a custom Android digital assistant that replaces Gemini/Google. It listens, speaks, and executes actions by connecting to your GPT/Nexus backend. Supports voice input, tool calls (dial, sms, navigate, torch, apps), and a dark Nexus theme with auto-built APK.
Nexus Assistant (Android)

Nexus Assistant is a custom Android digital assistant designed to replace Gemini/Google as your default system assistant. It connects directly to your Nexus/GPT backend, processes voice input, speaks responses, and executes real actions on your device with a sleek black/blue theme and alien branding.

✨ Features

Full System Assistant Integration
Set Nexus as your default digital assistant for long-press Power or swipe gestures.

Voice Input & TTS Output
Speech recognition captures your queries, Nexus backend responds, and results are spoken aloud.

Action Toolkit (JSON Tool Calls)

📞 Dial phone numbers

💬 Compose SMS messages

🗺 Start Google Maps navigation

🔦 Toggle flashlight

📅 Insert calendar events

⚙️ Open settings panels (Wi-Fi, Bluetooth, Location, Internet)

📲 Launch apps by package

Configurable Settings
Endpoint URL, optional API key, and “Speak responses” toggle.

Dark Nexus Theme
Matrix-style interface with alien head icon.

🚀 Quick Start

Upload this project to your GitHub repo.

Go to Actions → run Build Nexus Assistant → download the artifact app-debug.apk.

Transfer and install the APK on your Android phone.

Android Settings → Apps → Default Apps → Digital Assistant app → Nexus.

Open Nexus → ⚙️ → set your GPT/Nexus endpoint and API key.

🛠 How It Works

Nexus Assistant sends { "query": "…" } to your endpoint.

Your endpoint responds with either:

{ "reply": "…" } → Nexus speaks back, or

A tool call:

{
  "nexus_action": true,
  "tool": "navigate",
  "args": {"where": "123 Main St"},
  "say": "Starting navigation."
}


Nexus immediately executes the requested action.

📌 Notes

Direct toggles for Wi-Fi/BT are restricted by Android; Nexus opens the correct settings panel.

Flashlight control requires camera permission on first use.

You can expand with Shizuku or AccessibilityService for deeper system integration.
