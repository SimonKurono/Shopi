# 🛒 Shopi — Smart Reordering with Snap Spectacles

## Inspiration

Repeatedly running out of items and forgetting to reorder?
Tired of shopping lists and having to go order every single thing you need?

**Shopi** uses **Snap Spectacles** and real-time **computer vision** to monitor stock levels and automatically reorder items via **voice or gesture** using Snap Spectacles AR.


## ⚙️ What It Does

* Detects containers with low stock and surfaces replenishment prompts
* Processes images with **Gemini** via snap-and-buy
* Matches detected items to an **on-device catalog**
* Supports **hand-tracking**, **voice**, and **pinch** inputs
* Uses **AR overlays** and **TTS** for hands-free interaction
* Instantly prompts the **reorder of items**


## 🧠 How We Built It

### **Frontend (Snap Spectacles)**

* **Lens Studio** with TypeScript / JavaScript
* **Spectacles Interaction Kit v0.10.0** for hand gestures
* **HandVisual** for 3D tracking and visual feedback
* **Voice transcription** using Snap OS

### **Backend (FastAPI)**

* **Python 3+** with AsyncIO
* **ngrok** for server deployment
* **Pydantic** for schema validation
* **Gemini API (2.5 Flash)** for product detection and attribute identification
* **Selenium** for Shopify checkout automation
* **Google Search API** for product discovery and label-matching


## 🧩 Challenges We Ran Into

* **Spectacles hand tracking:** fixed by enabling disabled `HandVisual` components in the scene hierarchy
* **Image encoding:** handled large camera frames via base64 JPEG and browser telemetry
* **Product matching:** refined Gemini prompts to reduce false positives
* **Selenium automation:** overcame anti-bot defenses using randomized input timing


## 🏆 Accomplishments We’re Proud Of

* Working **AR glasses integration** with real-time vision
* **End-to-end path:** image → detection → catalog match → purchase
* Hands-free interaction via gestures
* Sub-second **AI responses** with caching
* Modular **FastAPI** design enabling future commerce integrations
* Stable build across **TS/JS (Lens Studio)** and **FastAPI** backends


## 📚 What We Learned

* Cross-platform performance needs **hardware-aware optimization**
* AR UI benefits from **gesture-driven controls** and minimal overlays
* Efficient **vision-processing pipelines** drastically reduce latency
* **Error handling** and graceful degradation are critical
* Fast iteration wins with **cloud AI**, while model fine-tuning remains niche
* **Generative AI prompts** must be specific to avoid bias or hallucination


## 🚀 What’s Next for Shopi

* Integrate **real-time object detection** (no snapshot required)
* Expand **voice-driven commerce** workflows
* Optimize for **battery and thermal performance** on Spectacles
* Explore **multimodal Gemini 3 API** for contextual purchase recommendations

