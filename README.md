# AETHER — Your Knowledge. Your AI. Anywhere.

> **AI for Better Living & Smarter Communities**  
> *PromptWars Bengaluru 2026 Submission*

[![Next.js 15](https://img.shields.io/badge/Next.js-15%20App%20Router-black?logo=next.js)](https://nextjs.org/)
[![TypeScript Strict](https://img.shields.io/badge/TypeScript-Strict%20Mode-blue?logo=typescript)](https://www.typescriptlang.org/)
[![WebLLM](https://img.shields.io/badge/Local%20AI-WebLLM%20%2B%20WebGPU-purple)](https://webllm.mlc.ai/)
[![IndexedDB](https://img.shields.io/badge/Storage-IndexedDB%20Offline-green)](https://developer.mozilla.org/en-US/docs/Web/API/IndexedDB_API)
[![Tests](https://img.shields.io/badge/Jest-27%20Passed-brightgreen)](https://jestjs.io/)

---

## 1. Product Vision & Problem Statement

In natural disasters, wilderness exploration, severe grid collapses, rural journeys, or humanitarian crises, **internet connectivity is the first infrastructure to fail**. Standard cloud AI assistants become completely useless the instant cellular data drops.

**AETHER** transforms your device into an autonomous, self-sufficient intelligence companion. It bridges the gap between online research and offline survival:

```
[ DESCRIBE ] ➔ [ RESEARCH ] ➔ [ PREPARE ] ➔ [ DOWNLOAD ] ➔ [ DISCONNECT ] ➔ [ ASK AI ]
```

1. **Describe**: State what you are planning or facing (*"Flood approaching my valley"*, *"Hiking Mount Washington"*, *"Living off-grid during a winter power outage"*).
2. **Research**: Online AI synthesizes verified civil defense protocols, emergency guides, and checklists.
3. **Prepare**: Review step-by-step checklists, medical protocols, and survival manuals.
4. **Download**: Cache complete kits, full markdown documents, and BM25 inverted vector index chunks into browser IndexedDB.
5. **Disconnect**: Sever cellular, satellite, and WiFi connection.
6. **Ask AI**: Query your offline library in real time using genuine browser-based AI inference.

---

## 2. Genuine Offline AI Architecture (Zero Cloud Dependency)

AETHER implements **real in-browser inference**, never substituting scripted answers or faking offline behavior:

```
┌────────────────────────────────────────────────────────────────────────┐
│                        AETHER CLIENT RUNTIME                           │
├────────────────────────────────────────────────────────────────────────┤
│                                                                        │
│  [ User Query ] ──▶ [ Sanitizer ] ──▶ [ Local Tokenizer & BM25 Match ] │
│                                                      │                 │
│                                                      ▼                 │
│                                           [ IndexedDB Chunks Store ]   │
│                                                      │                 │
│                                                      ▼                 │
│                                          [ Top-K Passages & Context ]  │
│                                                      │                 │
│                      ┌───────────────────────────────┴───────────────┐ │
│                      ▼                                               ▼ │
│          [ WebLLM WebGPU Engine ]                       [ Local Extractive RAG ]
│    (Llama-3.2-1B / SmolLM2-135M)               (BM25 Semantic Synthesizer)
│   • Runs on GPU via WebGPU                     • 100% offline on any browser
│   • In-browser neural weights                  • Zero GPU or RAM requirement
│   • Streams factual tokens                     • Direct section citations   
│                      │                                               │ │
│                      └───────────────────────────────┬───────────────┘ │
│                                                      ▼                 │
│                                          [ Verified Answer + Source ]  │
│                                          [ Audio Speech TTS Playback ] │
└────────────────────────────────────────────────────────────────────────┘
```

### The Two Complementary Inference Engines:
1. **WebLLM WebGPU Neural Engine**:
   - Executes quantized neural weights directly on device hardware (Llama 3.2 1B, SmolLM2 135M, Qwen 2.5 0.5B).
   - Real download progress callbacks, VRAM detection, and in-browser shader compilation.
   - Zero data leaves your device.
2. **AETHER Local Extractive RAG Synthesizer**:
   - High-precision BM25 passage scoring and extractive synthesis.
   - Strictly cites supporting document titles and sections.
   - **Guaranteed Hallucination Guard**: Explicitly flags `insufficient_evidence` when queried on topics not covered in your downloaded library.

---

## 3. Initial 10 Prepared Knowledge Kits

| Kit Title | Category | Verified Authority | Included Offline Assets |
|---|---|---|---|
| **1. Flood Preparedness & Flash Flood Survival** | Natural Disaster | FEMA / NOAA / Red Cross | 72h grab bag checklist, water boiling/chlorine dosing, electrical mains hazards, vehicle sinking escape. |
| **2. Hiking, Mountain Navigation & High Altitude** | Wilderness Safety | USFS / Mountain Rescue / WMS | Ten Essentials, hypothermia burrito wrap rewarming, STOP lost protocol, HAPE/HACE descent rules. |
| **3. First Aid & Emergency Triage Protocol** | Medical Life Support | AHA / TCCC / Red Cross | MARCH trauma algorithm, windlass tourniquet placement, hands-only CPR, Heimlich, shock positioning. |
| **4. Wilderness Camping & Bushcraft Survival** | Outdoor Safety | US Army FM 21-76 / NPS | Debris shelter thermodynamics, feather stick flint firecraft, bear country 100m triangle, distress smoke. |
| **5. Off-Grid Cooking & Pantry Rationing** | Daily Sustenance | FAO / USDA Food Safety | Haybox thermal retention cooking (saves 70% fuel), complete protein pairing, refrigerator cold chain timelines. |
| **6. International Travel & Consular Emergency** | Travel & Mobility | Bureau of Consular Affairs | Vienna Convention Article 36 detention rights, lost passport emergency replacement, 3-tier cash distribution. |
| **7. Accessibility & Medical Equipment Crisis** | Specialized Inclusion | FEMA Disability Integration | CPAP battery watt calculations, power wheelchair backup charging, service animal GO-bag, sensory visual cards. |
| **8. Offline STEM & Scientific Study Suite** | Education Resilience | NIST / IUPAC / OpenStax | Physical constants ($c$, $h$, $G$, $e$, $k$), single-variable calculus cheatsheet, thermodynamics laws. |
| **9. Grid Failure, Power Outages & Electrical Safety** | Urban Resilience | CPSC / OSHA / Ready.gov | Generator 20-ft carbon monoxide clearance, backfeeding electrocution warning, insulin cold-chain rules. |
| **10. Vehicle Breakdowns & Highway Emergencies** | Transit Safety | NHTSA / AAA Foundation | Star-pattern lug nut tire change on shoulder, 4-step jumpstart sequence, radiator steam explosion prevention. |

---

## 4. Integrated Offline Utilities

- **Offline Tactical Compass & GPS**: Hardware-direct magnetic orientation, live satellite coordinates (Lat, Lon, Alt, Accuracy), SOS clipboard broadcast, and offline waypoint bookmarks.
- **Emergency ICE Medical Card**: Client-encrypted medical profile (Blood type, Anaphylactic allergies, Daily prescriptions, ICE contacts, Family rendezvous point) with print/PDF export.
- **Survival & Water Dosing Calculator**: CDC bleach disinfection drops calculator, altitude boiling timer, Naismith's trail travel time estimator, and food rationing calculator.
- **Offline Field Logs & Notes**: IndexedDB markdown notebook with tag filtering and search.
- **Weather Snapshot & Barometric Guide**: Pre-departure weather logger and offline barometer/cloud observation guide.
- **Offline Storage & Quota Manager**: Direct inspection of `navigator.storage.estimate()` with selective or global cache purge.

---

## 5. Quick Start & Execution

### Prerequisites
- Node.js v18+ or v24+
- Modern Web Browser (Chrome, Edge, Firefox, Safari)

### Installation
```bash
# Clone or navigate into directory
cd d:/aether/aether

# Install dependencies
npm.cmd install

# Run automated test suite (all 27 tests pass)
npm.cmd test

# Start development server
npm.cmd run dev
```

Open **`http://localhost:3000`** in your browser.

---

## 6. Offline Verification Procedure (For Judges)

1. Open `http://localhost:3000`.
2. On the **Explore Kits** dashboard, click **"Download"** on **Flood Preparedness** or **Hiking & Mountain Safety**.
3. Notice the green **"Offline Ready"** badge appear.
4. Click the **"Simulate Offline"** button in the header (or physically disconnect your WiFi / turn on Airplane Mode).
5. Switch to the **AI Chat** tab.
6. Ask a specific practical question:
   - *"How many drops of bleach do I need to purify 5 liters of cloudy flood water?"*
7. Verify that:
   - The response is generated instantly on-device without cloud API requests.
   - The exact supporting source is cited: `Flash Flood Field Survival Manual > Water Purification`.
   - Click **"Listen Offline"** to hear the response read aloud via local OS speech synthesis.
8. Ask an unsupported question:
   - *"How do I assemble an orbital rocket engine?"*
9. Notice the **Insufficient Evidence** guard triggers, preventing dangerous hallucinations.

---

## 7. Security & Compliance

- **No Secrets Exposed**: All sensitive operations run client-side or use server-side environment variables (`GEMINI_API_KEY`).
- **Prompt Injection Hardening**: `sanitizeForPrompt` neutralizes delimiter breakouts, command overrides, control characters, and `<script>` injections.
- **Strict CSP**: Content Security Policy in `next.config.ts` prevents unauthorized scripts and external exfiltration while allowing WebGPU/Wasm model weights.
- **Data Privacy**: All personal medical data, notes, and chat transcripts remain strictly inside the user's browser IndexedDB.

---

*Built with passion for prompt engineers, first responders, outdoor adventurers, and disconnected communities worldwide.*
