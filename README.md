# Nexus Assistant (Android)

A minimal, dark-themed Android assistant that replaces Gemini/Google as your system assistant,
pipes speech to your Nexus (GPT) endpoint, speaks back with TTS, and **executes actions** via a simple tool registry.

## What it can do now
- System assistant intent (`ACTION_ASSIST`): long-press or assistant gesture opens Nexus.
- Voice in → sends to your Nexus endpoint (`/chat`) → parses JSON tool calls.
- Built‑in tools: `dial`, `sms`, `navigate`, `open_app`, `torch` (flashlight), `open_settings`, `calendar_insert`.
- Settings screen to set **Endpoint URL** and optional **API key**.
- Black/blue Nexus theme + alien icon.

## Quick install (no coding)
1. Zip already includes a GitHub Actions workflow.
2. Create a new GitHub repo and upload this folder.
3. Go to **Actions** → wait for the **Build Nexus Assistant** job → **Download Artifact** → you'll get `app-debug.apk`.
4. Sideload on your phone. Then set **Settings → Apps → Default Apps → Digital Assistant → Nexus**.
5. Open Nexus → tap the gear (bottom-right) and set **Endpoint URL** to your GPT/Nexus HTTP endpoint.

## Expected endpoint format
POST `Endpoint URL` with JSON body:
```json
{ "query": "text user said" }
```
Respond with either:
```json
{ "reply": "text to speak back" }
```
or a tool call:
```json
{ "nexus_action": true, "tool": "navigate", "args": {"where": "123 Main St"}, "say": "Starting navigation."}
```

## Permissions
- Microphone (speech recognition)
- Internet
- Camera (for torch control)

> Note: Direct Wi‑Fi/BT toggles are restricted on modern Android; `open_settings` opens the relevant panel.
> For deeper control, consider Shizuku or an AccessibilityService (not included by default).

## Build locally (optional)
- Install Android Studio (JDK 17).
- Open project → Run.
- Debug APK is at `app/build/outputs/apk/debug/app-debug.apk`.

Enjoy.
