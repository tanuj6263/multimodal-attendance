# Multimodal Attendance & Engagement Agent

An AI-powered, privacy-preserving classroom intelligence system that integrates computer vision, audio signal processing, and agent-based reasoning. The system automatically tracks attendance based on sustained presence, analyzes engagement trends, and provides AI-driven, context-aware teaching suggestions—operating entirely offline to ensure data privacy and ethical deployment.

## 🚀 Project Overview

Traditional attendance tracking is time-consuming and fails to capture student engagement context. This project bridges that gap by providing educators with real-time, actionable insights into classroom dynamics, allowing them to optimize session effectiveness and adapt their teaching methodologies on the fly.

### Core Scenarios Supported
1. **Automated Attendance Tracking:** Processes live or recorded video feeds to track participants. Marks attendance based on sustained presence rather than single-frame detection to drastically reduce false positives.
2. **Engagement & Session Dynamics Analysis:** Continuously fuses multimodal signals (head pose estimation, movement patterns, inactivity duration, and audio activity) to map engagement trends over discrete time intervals.
3. **AI-Driven Teaching Suggestions:** Generates context-aware, assistive suggestions for instructors (e.g., prompting interactive activities or adjusting pacing) based on detected engagement drops or interaction peaks.

---

## 🏗️ Technical Architecture & Project Structure

The project is structured modularly to align with step-by-step development phases:

```text
multimodal-attendance-agent/
├── README.md
├── requirements.txt
├── config.yaml
├── vision_module/
│   ├── __init__.py
│   ├── face_detector.py      # Face detection & sustained tracking
│   └── pose_estimator.py     # Head pose estimation & movement patterns
├── audio_module/
│   ├── __init__.py
│   └── audio_processor.py    # Voice activity detection & volume levels
├── analytics_engine/
│   ├── __init__.py
│   ├── fusion.py             # Fuses vision and audio signal vectors
│   └── agent_reasoning.py    # Local rule/model engine for pedagogical alerts
└── app/
    ├── __init__.py
    ├── interface.py          # Dashboard UI (Streamlit / Gradio)
    └── database.py           # Offline storage for logs (SQLite)
```

---

## ⚙️ System Requirements

### Hardware Requirements
* **Processor:** Intel Core i5 (8th Gen or above) / AMD Ryzen 5 or equivalent
* **RAM:** Minimum 8 GB (Recommended: 16 GB for multitasking and local inference)
* **Storage:** 256 GB SSD minimum (or 500 GB HDD minimum)

### Software Requirements
* **Operating System:** Windows 10 / 11, macOS (Monterey or later), or Linux (Ubuntu 20.04+)
* **Development Environment:** Python (version 3.8 or above), Git, Visual Studio Code (Recommended)

---

## 🛠️ Step-by-Step Implementation Workflow

### EPIC 1: Requirements Specification and Environment Setup
* [ ] Initialize Git repository and structure directories.
* [ ] Create virtual environment and install standard dependencies (`opencv-python`, `numpy`, `scipy`).
* [ ] Configure baseline workspace configurations (`config.yaml`).

### EPIC 2: Vision Module Development
* [ ] Implement localized face detection utilizing lightweight models (e.g., Haar Cascades or MediaPipe Face Mesh).
* [ ] Build a sustained presence verification algorithm tracking bounding boxes over predefined frame intervals ($N$ consecutive seconds).
* [ ] Integrate head pose estimation matrix computations to extract pitch, yaw, and roll vectors for attentiveness indexing.

### EPIC 3: Audio Module Development
* [ ] Build continuous audio stream capturing via standard microphone hardware hooks.
* [ ] Deploy Voice Activity Detection (VAD) rules to separate ambient classroom noise from active vocal interactions.
* [ ] Log discrete timestamped volume spikes and silence durations to flag active discussions or sudden drops in class interaction.

### EPIC 4: AI Implementation & Data Fusion
* [ ] Build a localized algorithmic layer to sync video timestamps directly with audio event logs.
* [ ] Develop a custom heuristics matrix mapping mixed signals (e.g., low movement + zero audio = high risk of absolute passivity).
* [ ] Ensure all computing happens completely localized on device with zero external APIs, enforcing absolute data privacy.

### EPIC 5: Analytics & Recommendation Engine
* [ ] Write an engine that flags critical classroom attention drops lasting longer than a set window (e.g., 5 minutes).
* [ ] Design a structured rule template mapping classroom states to context-aware pedagogical hints (e.g., *"Engagement down by 30%—consider launching an interactive quiz"*).
* [ ] Hook up an offline SQLite session database to record analytics seamlessly without data leaks.

### EPIC 6: Interface, Testing, and Deployment
* [ ] Construct a clean, accessible layout using an interactive local framework like Streamlit.
* [ ] Run simulated validation tracks simulating empty rooms, dynamic interactions, and sudden room exits to verify threshold tuning.
* [ ] Export production-ready execution scripts (`run.py`) alongside documentation to deploy locally.

---

## 💻 Quick Start (Mock Initial Setup)

1. **Clone the repository:**
   ```bash
   git clone https://github.com/YOUR_USERNAME/multimodal-attendance-engagement-agent.git
   cd multimodal-attendance-engagement-agent
   ```

2. **Set up virtual environment:**
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows use: venv\Scripts\activate
   ```

3. **Install planned core packages:**
   ```bash
   pip install opencv-python numpy streamlit pyyaml
   ```

4. **Run mock verification entry point:**
   ```bash
   python app/interface.py
   ```
