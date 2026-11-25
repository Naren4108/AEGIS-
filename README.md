# Aegis – Women's Safety & Security (prototype)

## Folder
- index.html – the whole prototype (UI, shake SOS, recording, messaging, police console, safe journey, stealth mode)
- manifest.json, sw.js – make it installable ("Add to Home Screen") and cached offline
- assets/ – logo and app icons
- docs/ROADMAP.md – what is simulated and what the real build needs

## Run it
Camera, microphone, location and shake sensors need HTTPS (or localhost):
    cd aegis-app && python3 -m http.server 8000      # then open http://localhost:8000
For a phone, host the folder on any HTTPS host (GitHub Pages, Netlify, Firebase Hosting).

## Important
- The cross-device sync (guardian alerts, messages, police console) uses the claude.ai
  artifact database. Outside claude.ai it is absent, so the app runs in offline mode:
  SOS, recording and shake work, but guardians/police on other devices are NOT reached.
  The real backend (Firebase or Node) replaces this: see docs/ROADMAP.md.
- Police login (POLICE01 / 1234) is a demo only. Never ship credentials in client code.
- To make an APK: host the folder over HTTPS, then use PWABuilder.com (or Capacitor) to package it.
  A full native Android app (Kotlin) is still needed for automatic SMS, call-log access and
  calls that keep recording.
