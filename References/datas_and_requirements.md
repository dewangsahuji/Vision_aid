Perfect, Dewang 🔥 — now you’re thinking like a *real AI developer*.
To make **VisioAid Mobile** fully functional, you’ll need datasets, pretrained models, and resources for each of your app’s modules (Object Detection, OCR, Face, etc.).

Below is a **complete curated list** of everything — datasets, model links, and setup resources for training, conversion, and mobile optimization 👇

---

# 🧠 **VisioAid Mobile — Datasets & Resources Repository**

### 📁 **Goal:**

To give you **all datasets, pretrained models, and training sources** for every module of the app — optimized for **Python + Kivy (mobile)** and **offline AI inference**.

---

## ⚙️ **1. Object Detection**

**Purpose:** Identify nearby objects (person, chair, car, door, stairs, etc.)

| Type                       | Resource                                                                              | Description                                         |
| -------------------------- | ------------------------------------------------------------------------------------- | --------------------------------------------------- |
| ✅ **Pretrained Model**     | [YOLOv8n (Ultralytics)](https://github.com/ultralytics/ultralytics)                   | Lightweight and mobile-ready object detection model |
| 📦 **Dataset**             | [COCO 2017 Dataset](https://cocodataset.org/#download)                                | 80-class dataset for general objects                |
| 📚 **Alternative Dataset** | [Open Images Dataset V7](https://storage.googleapis.com/openimages/web/download.html) | Large-scale multi-object detection dataset          |
| 🧰 **Model Conversion**    | Export YOLOv8 → `.tflite` using:  <br> `yolo export format=tflite imgsz=320`          |                                                     |

🧠 **Tip:** Fine-tune YOLOv8 on your own collected “indoor navigation” dataset for better real-world accuracy.

---

## 📖 **2. OCR (Text Reading)**

**Purpose:** Read printed or handwritten text in real time

| Type                       | Resource                                                                                | Description                                      |
| -------------------------- | --------------------------------------------------------------------------------------- | ------------------------------------------------ |
| ✅ **Library**              | [EasyOCR](https://github.com/JaidedAI/EasyOCR)                                          | Multilingual OCR (supports Hindi, English, etc.) |
| 🧾 **Dataset (optional)**  | [ICDAR 2013/2015 Scene Text](https://rrc.cvc.uab.es/)                                   | For training or improving OCR accuracy           |
| 🌍 **Alternative**         | [PaddleOCR](https://github.com/PaddlePaddle/PaddleOCR)                                  | Faster inference and supports quantization       |
| 🧰 **Mobile Optimization** | Convert EasyOCR model to TFLite using `torch2tflite` or export PaddleOCR model directly |                                                  |

---

## 💵 **3. Currency Recognition (Indian Notes)**

**Purpose:** Identify Indian Rupee denominations via camera

| Type                       | Resource                                                                                                                       | Description                                |
| -------------------------- | ------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------ |
| 🧾 **Dataset**             | [Kaggle - Indian Currency Notes Dataset](https://www.kaggle.com/datasets/shivamkushwaha/banknote-dataset)                      | High-quality INR images for classification |
| 🧾 **Alternative Dataset** | [Kaggle - Indian Currency Recognition Dataset](https://www.kaggle.com/datasets/iamsouravbanerjee/indian-currency-note-dataset) | 6 denominations, ready for CNN             |
| ✅ **Model**                | MobileNetV3 / EfficientNet-B0 (pretrained on ImageNet)                                                                         |                                            |
| ⚙️ **Training Framework**  | TensorFlow or PyTorch with transfer learning                                                                                   |                                            |
| 📱 **Convert to Mobile**   | Use TensorFlow Lite Converter:  <br>`tflite_convert --saved_model_dir=model --output_file=currency_model.tflite`               |                                            |

---

## 😀 **4. Face & Emotion Recognition**

**Purpose:** Identify known people + detect emotions (happy, sad, neutral, etc.)

| Type                            | Resource                                                                                                        | Description          |
| ------------------------------- | --------------------------------------------------------------------------------------------------------------- | -------------------- |
| 🧾 **Face Dataset**             | [VGGFace2](https://www.robots.ox.ac.uk/~vgg/data/vgg_face2/)                                                    | For face embeddings  |
| 🧾 **Emotion Dataset**          | [FER2013](https://www.kaggle.com/datasets/msambare/fer2013)                                                     | 7 emotion categories |
| ✅ **Models**                    | [FaceNet](https://github.com/davidsandberg/facenet) / [InsightFace](https://github.com/deepinsight/insightface) |                      |
| 🧠 **Lightweight Alternatives** | [MobileFaceNet](https://github.com/sirius-ai/MobileFaceNet_TF) + small FER CNN                                  |                      |
| 🔁 **Conversion**               | Convert embeddings and models to ONNX / TFLite for speed                                                        |                      |

🧰 **Extra Tip:** Store user face embeddings in `face_embeddings.pkl` for on-device matching.

---

## 🌄 **5. Scene Description (Captioning)**

**Purpose:** Generate natural language captions like “A person walking near a table.”

| Type                                 | Resource                                                                                 | Description |
| ------------------------------------ | ---------------------------------------------------------------------------------------- | ----------- |
| 🧾 **Pretrained Model**              | [BLIP (HuggingFace)](https://huggingface.co/Salesforce/blip-image-captioning-base)       |             |
| 🧠 **Alternative Lightweight Model** | [ViT-GPT2 Image Captioning](https://huggingface.co/nlpconnect/vit-gpt2-image-captioning) |             |
| 📚 **Dataset**                       | [MS COCO Captions Dataset](https://cocodataset.org/#download)                            |             |
| ⚙️ **Optimization**                  | Use ONNX Runtime for faster inference on mobile                                          |             |
| 💡 **Integration**                   | Output text → VoiceAgent (TTS) → spoken scene summary                                    |             |

---

## 🧭 **6. Navigation & Safety (Obstacle Detection)**

**Purpose:** Detect proximity and warn about obstacles in real time

| Type                     | Resource                                                                                            | Description |
| ------------------------ | --------------------------------------------------------------------------------------------------- | ----------- |
| 🧾 **Dataset**           | [Depth Estimation Dataset (NYU Depth V2)](https://cs.nyu.edu/~silberman/datasets/nyu_depth_v2.html) |             |
| ✅ **Model**              | [MiDaS](https://github.com/isl-org/MiDaS) for monocular depth estimation                            |             |
| ⚙️ **Optimization**      | Use **MiDaS small** model variant for real-time use                                                 |             |
| 🧠 **Additional Source** | [Obstacle Detection Dataset (Roboflow)](https://universe.roboflow.com/)                             |             |

🧰 **Implementation:**
Combine MiDaS depth map + YOLO detections → calculate distance threshold → trigger voice/vibration alert.

---

## 🗣️ **7. Speech Modules (Voice Input/Output)**

**Purpose:** Take all input and output via voice

| Type                        | Resource                                                                    | Description |
| --------------------------- | --------------------------------------------------------------------------- | ----------- |
| 🎤 **STT (Speech-to-Text)** | [Vosk](https://alphacephei.com/vosk/models) — offline multilingual model    |             |
| 🧠 **Alternative**          | [Whisper.cpp](https://github.com/ggerganov/whisper.cpp) — runs locally      |             |
| 🔊 **TTS (Text-to-Speech)** | [Coqui TTS](https://github.com/coqui-ai/TTS) — high quality voice synthesis |             |
| 💡 **Light Alternative**    | [pyttsx3](https://pyttsx3.readthedocs.io/en/latest/) — works offline        |             |

🧰 **Integration Example:**

```
command = listen()  
response = decision_agent.handle(command)  
speak(response)
```

---

## 🧩 **8. Agentic Reasoning (AI Brain)**

**Purpose:** Contextual understanding + intelligent decisions

| Type                     | Resource                                                                                                           | Description |
| ------------------------ | ------------------------------------------------------------------------------------------------------------------ | ----------- |
| 🤖 **Framework**         | [LangChain](https://github.com/langchain-ai/langchain)                                                             |             |
| 🧠 **Model Options**     | [Phi-3 Mini](https://huggingface.co/microsoft/Phi-3-mini-4k-instruct), [Llama 3](https://ollama.ai/library/llama3) |             |
| ⚙️ **Integration**       | Lightweight LLM for mobile reasoning                                                                               |             |
| 💾 **Memory**            | [FAISS](https://github.com/facebookresearch/faiss) + SQLite                                                        |             |
| 💬 **Offline Reasoning** | Run LLM via [Ollama](https://ollama.ai/download) (on-device)                                                       |             |

---

## 💾 **9. Utilities & Tools**

| Purpose           | Tool                                                                 |
| ----------------- | -------------------------------------------------------------------- |
| Data labeling     | [Roboflow](https://roboflow.com/)                                    |
| Model compression | [TensorFlow Lite Converter](https://www.tensorflow.org/lite/convert) |
| On-device testing | [Termux + Buildozer](https://github.com/kivy/buildozer)              |
| Voice testing     | [pyaudio](https://people.csail.mit.edu/hubert/pyaudio/)              |
| Edge optimization | [ONNX Runtime Mobile](https://onnxruntime.ai/)                       |

---

## 📦 **10. Model File Summary for /models Folder**

| File                    | Description                |
| ----------------------- | -------------------------- |
| `yolov8n.tflite`        | Object Detection           |
| `currency_model.tflite` | Currency Classifier        |
| `face_embeddings.pkl`   | Stored known faces         |
| `emotion_model.tflite`  | FER (Emotion Recognition)  |
| `blip_model/`           | Scene Captioning Model     |
| `vosk_model/`           | Offline Speech Recognition |
| `midas_small.onnx`      | Depth Estimation           |
| `faiss_index.bin`       | Context Memory Store       |

---

## 🚀 **11. Recommended Hardware for Testing**

| Device    | Specs                                 |
| --------- | ------------------------------------- |
| Android   | 4GB RAM minimum, Camera + Mic enabled |
| OS        | Android 10+                           |
| Processor | Snapdragon 730 or above               |
| Optional  | External mic (for clear STT)          |

---

## ✅ **12. Final Integration Tips**

* Quantize all models to **INT8 or FP16** for mobile.
* Use **multithreading** in Kivy for voice and camera loops.
* Combine **YOLO + BLIP + OCR** results for richer context.
* Cache **previous detections** in SQLite for faster repeats.
* Always test modules individually before merging.

---

Would you like me to now prepare a **ZIP package structure (folders + placeholders)** for all these datasets and models, so you can directly plug it into your project directory (`VisioAidMobile/`)?
It will include all folder names, README links, and model placement structure — ready for download.
