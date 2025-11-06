🧩 1. App Overview

Type: Cross-platform AI app (Android + iOS)
Interface: Voice-only (optional simple UI)
Core: Python backend (Flask/FastAPI) + Mobile front-end (Kivy/Flutter)
Mode: Works fully offline
Purpose: Computer vision + speech + AI reasoning on-device

-----------------------------------------------------------------------------------------

⚙️ 3. Technology Stack

| **Layer**              | **Tool / Library**                               |
| ---------------------- | ------------------------------------------------ |
| **Frontend**           | Kivy (Python UI) / Flutter *(optional)*          |
| **Backend**            | FastAPI / Flask                                  |
| **Speech Recognition** | Whisper.cpp *(offline)* / Vosk                   |
| **Text-to-Speech**     | Edge-TTS / Coqui-AI / pyttsx3                    |
| **Computer Vision**    | OpenCV / YOLOv8n / EasyOCR / BLIP                |
| **AI Reasoning**       | LangChain / Phi-3-mini / Llama3 / Ollama         |
| **Database**           | SQLite + FAISS                                   |
| **Sensors**            | Android API *(via Pyjnius / Flutter plugins)*    |
| **Packaging**          | Buildozer *(Kivy → Android APK)* / Flutter build |


-----------------------------------------------------------------------------------------

🧠 5. Core Features (Technical Implementation)
Feature	Implementation
🎙️ Voice Commands	Whisper.cpp for STT → LangChain parser → executes module
🔊 Voice Output	Edge-TTS → AudioQueue playback
👁️ Object Detection	YOLOv8n → bounding boxes → spoken output
📖 Text Reader	EasyOCR → extracted text → summarized via LLM → TTS
💵 Currency Detector	MobileNetV3 → predicts denomination
😀 Face Recognition	FaceNet + embedding database
🧭 Navigation Guidance	Camera + GPS (if outdoors) → simple directional speech
⚙️ Agentic Decisions	DecisionAgent routes tasks intelligently
🧩 Context Awareness	Logs user actions + last environment
🧬 Offline Mode	All inference done locally (TFLite / ONNX)

-----------------------------------------------------------------------------------------

⚡ 8. Phase-Wise Development Plan (8 Weeks)
Week	Task	Deliverable
1	Setup Kivy UI + TTS	App speaks messages
2	Integrate Whisper STT	Speech → Text commands
3	Add Object Detection	Camera → Object → Voice output
4	Add OCR + Currency	Text reading + note recognition
5	Add LLM + LangChain	Intent routing (agentic brain)
6	Add Face + Navigation	FaceNet + GPS integration
7	Add Context Memory	SQLite + FAISS memory system
8	Optimize + Build APK	Fully offline, production-ready APK

-----------------------------------------------------------------------------------------
🧰 9. Model Suggestions (Lightweight for Mobile)

| Task             | Model                  | Format           |
| ---------------- | ---------------------- | ---------------- |
| STT              | Whisper Tiny / Vosk    | `.bin` / `.onnx` |
| Object Detection | YOLOv8n                | `.tflite`        |
| OCR              | EasyOCR (light)        | Python model     |
| Scene Captioning | BLIP base              | ONNX             |
| Face Recognition | MobileFaceNet          | `.tflite`        |
| Emotion          | FER Tiny               | `.tflite`        |
| Reasoning        | Phi-3 Mini / Llama3 1B | Ollama local     |
| TTS              | Edge-TTS / Coqui       | Local or API     |

---------------------------------------------------------------------------------------

🔒 10. Privacy & Offline Capabilities

✅ No data leaves device
✅ All inference offline (TFLite / ONNX)
✅ Encrypted local memory (SQLite + AES)
✅ Optional cloud sync via user permission

---------------------------------------------------------------------------------------

✅ 12. Final Output

App Name: VisioAid
Platform: Android (primary), iOS (future)
Core: AI + CV + Speech + Agents
Operation: 100% Voice-based
USP: Offline, private, and accessible






