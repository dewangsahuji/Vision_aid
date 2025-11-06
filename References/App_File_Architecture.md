VisioAidMobile/
│
├── app.py                   # Entry point (FastAPI or controller)
│
├── agents/
│   ├── voice_agent.py
│   ├── decision_agent.py
│   ├── perception_agent.py
│   ├── context_agent.py
│   ├── safety_agent.py
│   └── knowledge_agent.py
│
├── modules/
│   ├── object_detector.py
│   ├── ocr_reader.py
│   ├── scene_captioner.py
│   ├── currency_detector.py
│   ├── face_recognizer.py
│   └── navigation_helper.py
│
├── utils/
│   ├── tts.py
│   ├── stt.py
│   ├── gps_manager.py
│   ├── memory_db.py
│   └── config.py
│
├── ui/
│   ├── main.kv               # Kivy UI layout
│   └── app_controller.py
│
├── models/
│   ├── yolov8n.tflite
│   ├── currency_model.tflite
│   ├── face_embeddings.pkl
│   └── blip_model/
│
└── requirements.txt







VisioAidMobile/
│
├── main.py                     # Main Kivy App (UI + loop)
│
├── agents/
│   ├── voice_agent.py          # Voice input/output (STT + TTS)
│   ├── decision_agent.py       # Parses voice commands → triggers modules
│   ├── perception_agent.py     # Handles object, OCR, face, scene
│   ├── context_agent.py        # Saves memory / context of last actions
│   ├── safety_agent.py         # Fall detection / emergency triggers
│   └── knowledge_agent.py      # Scene summarization / LLM responses
│
├── modules/
│   ├── object_detector.py      # YOLOv8n.tflite object detection
│   ├── ocr_reader.py           # EasyOCR text extraction
│   ├── scene_captioner.py      # BLIP scene description
│   ├── currency_detector.py    # CNN for INR recognition
│   ├── face_recognizer.py      # FaceNet for known faces
│   ├── emotion_detector.py     # FER model
│   └── depth_estimator.py      # MiDaS or OpenCV disparity
│
├── utils/
│   ├── tts.py                  # Edge-TTS / pyttsx3 speech output
│   ├── stt.py                  # Whisper.cpp / Vosk
│   ├── config.py               # Model paths, thresholds, etc.
│   ├── memory_db.py            # SQLite memory + FAISS
│   └── gps_manager.py          # Optional GPS integration
│
├── ui/
│   ├── main.kv                 # Kivy UI file
│   └── app_controller.py       # Controls the app flow + agent coordination
│
├── models/
│   ├── yolov8n.tflite
│   ├── currency_model.tflite
│   ├── face_embeddings.pkl
│   ├── emotion_model.tflite
│   └── blip_model/
│
└── requirements.txt



















