# Smart Health Companion

A polished, interactive HealthTech prototype that combines simulated phone/wearable health data with environmental conditions to surface possible risk patterns — heat stress, poor air quality, and low recovery/sleep — through a simple rule-based risk engine and an AI-generated, plain-language explanation.

**This is a demo/prototype. It is not a medical device and does not diagnose anything.**

🔗 Live demo: https://obitorinai.github.io/Ayu_sheld/

---

## What it does

```
Phone / Wearable data
        +
Environmental data
        +
User profile / baseline
        ↓
Risk / Rule Engine
        ↓
Structured risk result
        ↓
AI explanation (optional)
        ↓
Dashboard / Alert
```

- **Onboarding** — a short four-step questionnaire (name, age, sex, city, work type, height, weight, activity level, usual sleep, optional emergency contact) that personalizes the dashboard in real time.
- **Dashboard** — wellness score, health status card, live health metric cards (heart rate, SpO₂, temperature, activity, sleep, hydration) with interactive charts, an AI health insight card, environment preview, weekly steps chart, and nearest-care list.
- **Environment & Map** — current conditions (temperature, humidity, wind, UV, AQI), environmental risk indicators, and a demo map with hospitals, pharmacies, and emergency facilities.
- **Risk Center** — current risk level, category breakdown (health pattern, heat stress, environmental exposure, recovery, disaster), and alert history.
- **Profile & Settings** — editable personal/lifestyle info and a privacy center with permission toggles.
- **Demo Control** — switch between four scenarios (Normal, Heat Stress, High Pollution, Poor Sleep/Recovery) or run an animated timeline simulation that walks through data → analysis → risk detection → AI explanation → alert.
- **Floating alerts** — when a scenario triggers a risk, a dismissible banner surfaces the contributing vitals and the nearest demo hospital.

## Tech

Single self-contained `smart-health-companion.html` file — vanilla JS, no build step, no dependencies. Everything (styles, state, scenario data, risk engine, chart rendering, and views) lives in one file so it can be opened directly in a browser or hosted anywhere static files are served.

## Getting started

```bash
git clone <your-repo-url>
cd <your-repo>
open smart-health-companion.html   # or just double-click the file
```

No install step, no environment variables required to run the demo.

## Project structure

Currently a single file:

```
smart-health-companion.html   # markup, styles, state, scenario/risk engine, all views
```

A modular version (separate scenario data, risk service, and components) is available on request and mirrors this structure:

```
src/
  data/scenarios.ts       # centralized demo scenarios + synthetic history generator
  services/riskService.ts # rule-based risk engine + AI insight service
```

## Demo data & AI

All health, environment, and hospital data in this prototype is **synthetic** and clearly labeled "Demo data" in the UI. There is no live weather, air-quality, or hospital-availability integration in this version.

The AI explanation layer only ever receives a structured risk result (type, severity, confidence, contributing factors) — never raw health data — and falls back to a built-in plain-language explanation if no AI backend is configured, so the app works fully offline.

## Safety & scope

This prototype intentionally avoids diagnostic language. It uses phrasing like "possible risk," "may indicate," and "consider taking precautions," and never claims to diagnose, treat, or prevent any condition. It is intended purely to demonstrate the interaction between health signals, environment, risk logic, and AI explanation.

## Roadmap (not implemented)

- Real weather / AQI / places API integration behind the existing service abstractions
- Firebase Authentication + Realtime Database persistence
- Wearable / Health Connect integration
- Map drag-to-pan

## License
M.I.T LICENSE 

