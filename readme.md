# Run 5 AI Models on Raspberry Pi – Complete Setup Guide

> This project shows how to install and run **5 different AI models** on a Raspberry Pi (tested on Raspberry Pi 4B, 64-bit OS).

## Models Covered

1. **LLM (Language Model)** – TinyLLaMA & Deepseek-Coder via Ollama
2. **Vision (Object Detection)** – SSD Mobilenet
3. **STT (Speech to Text)** – OpenAI Whisper.cpp
4. **TTS (Text to Speech)** – Coqui TTS
5. **Face Filter** – MediaPipe + FaceMesh with Iron Man overlay

---

## Installation Commands

### Update and Upgrade

```bash
sudo apt update && sudo apt upgrade -y
```

### LLM – TinyLLaMA & Deepseek-Coder via Ollama

```bash
curl -fsSL https://ollama.com/install.sh | sh
ollama run tinyllama
ollama run deepseek-coder:1.3b
```

### Vision – SSD Mobilenet (TFLite)

```bash
sudo apt install wget unzip -y

# Download model
wget https://storage.googleapis.com/download.tensorflow.org/models/tflite/coco_ssd_mobilenet_v1_1.0_quant_2018_06_29.zip
unzip coco_ssd_mobilenet_v1_1.0_quant_2018_06_29.zip

# Download label map
wget https://raw.githubusercontent.com/tensorflow/models/master/research/object_detection/data/mscoco_label_map.pbtxt -O labels.txt
```

### STT – Whisper.cpp (Speech to Text)

```bash
sudo apt install -y build-essential cmake git ffmpeg

git clone https://github.com/ggerganov/whisper.cpp
cd whisper.cpp
make
./models/download-ggml-model.sh tiny.en
```

### TTS – Coqui TTS

```bash
# Avoiding sudachipy and spacy[ja]
pip install TTS

# If needed for compatibility
pip install bnnumerizer bnunicodenormalizer gruut[de,es,fr]==2.2.3 hangul_romanize numpy==1.24.3 --break-system-packages
```

### Face Filter – MediaPipe + FaceMesh

```bash
pip install mediapipe opencv-python numpy 
```

---

## Watch the Full Video

> [YouTube Link Here](https://youtu.be/9OehZ2zKyt8) 

## Applications

* Build local AI assistants
* Do offline speech recognition
* Create interactive face filters
* Run AI with no cloud needed

---

## Feedback

If you try this on your Raspberry Pi, let me know how it goes! Drop issues, ideas, or cool use cases in the comments or open a pull request.

---

© 2025 – Jack of All - Tech
