🎧 AI AudioBook Generator

The **AI AudioBook Generator** is an advanced application that transforms text documents into expressive, human-like audiobooks.  
It extracts text from various file formats, rewrites it in a storytelling style using **Gemini LLM**, and converts it into natural speech using **Coqui TTS** or **pyttsx3**.

This updated version includes secure API handling using a **.env** file and a centralized configuration system via **config.py**.

---

## 🚀 Project Overview

This system provides a fast and accessible way for users to consume text content through audio.  
It is particularly beneficial for:

- Students  
- Professionals  
- Visually impaired users  
- Content creators  
- People who prefer listening over reading  

**Workflow:**  
`Upload Document → Extract Text → Enrich Narration Using AI → Convert to Speech → Download Audiobook`

---

## 🧩 Features

- Upload PDF / DOCX / TXT documents  
- Automatic text extraction  
- Gemini AI-based audiobook-style narration enhancement  
- Natural speech generation with Coqui TTS  
- Offline TTS fallback via pyttsx3  
- Clean, interactive Streamlit UI  
- Secure API key storage using `.env`  
- Centralized configuration via `config.py`

---

## 🏗 System Architecture

AI-AudioBook-Generator/
│
├── app.py # Streamlit user interface
├── config.py # Loads .env and manages global settings
├── llm_enrichment.py # Gemini AI narration enhancement
├── text_extraction.py # PDF/DOCX/TXT text extraction
├── tts_generator.py # Coqui TTS + pyttsx3 audio generation
├── requirements.txt # Python dependencies
└── README.md # Project documentation

yaml
Copy code

---

## 🔐 Environment Setup (.env)

Create a `.env` file in your project root:

GEMINI_API_KEY=your_gemini_api_key_here
OPENAI_API_KEY=your_openai_api_key_here

TTS_ENGINE=coqui
TTS_OUTPUT_FORMAT=wav

DEBUG_MODE=False

yaml
Copy code

> ⚠️ Ensure `.env` is added to `.gitignore` to keep keys secure.

---

## 📦 Installation

### 1️⃣ Clone the Repository
```bash
git clone https://github.com/yourusername/AI-AudioBook-Generator.git
cd AI-AudioBook-Generator
2️⃣ Create & Activate Virtual Environment
bash
Copy code
python -m venv env
source env/bin/activate       # macOS/Linux
env\Scripts\activate          # Windows
3️⃣ Install Dependencies
bash
Copy code
pip install -r requirements.txt
4️⃣ Install System Dependencies
Windows
Install eSpeak NG

Add it to PATH

Restart terminal

Ubuntu / Linux
bash
Copy code
sudo apt update
sudo apt install espeak-ng
macOS
bash
Copy code
brew install espeak
🔑 API Configuration
Generate your Gemini API key at:
https://makersuite.google.com/app/apikey

Set it inside your .env file.

The project automatically loads API keys using:

python
Copy code
from config import GEMINI_API_KEY
🖥 Usage
Run the application:
bash
Copy code
streamlit run app.py
Inside the UI:
Upload a document (PDF/DOCX/TXT)

Preview extracted text

Click "Generate Audiobook"

Listen or download the audio file

🧠 How It Works (Detailed)
1. Text Extraction
PyPDF2 & pdfplumber for PDFs

python-docx for DOCX

Direct reading for TXT

2. LLM Narration Enhancement
Gemini rewrites the text into audiobook-style narration

Chunking prevents token overflow

Final enriched text is smoother and more expressive

3. Text-to-Speech Generation
Coqui TTS (primary engine)

pyttsx3 (offline fallback)

Output format controlled via .env

4. Streamlit UI
Handles uploads, previews, progress, playback, and downloads

🧪 Testing
Unit Testing
Verified extraction, rewriting, and audio synthesis independently

Integration Testing
Ensured all modules work together in sequence smoothly

Performance Testing
Measured audio generation time for different document sizes

Fallback Testing
Verified pyttsx3 activates when Coqui fails

🚀 Deployment Options
Streamlit Cloud

Hugging Face Spaces

Docker Containers

Local/On-premise deployment

Add environment variables in deployment settings for .env compatibility.

🧰 Tech Stack
Python 3.11

Streamlit (UI)

Gemini AI (Narration enhancement)

Coqui TTS / pyttsx3 (Speech synthesis)

PyPDF2, pdfplumber, python-docx (Text extraction)

dotenv (Environment variable management)

🧩 Future Enhancements
Multi-voice selection

Multi-language audiobook generation

Background music mixing

Chapter-wise audio segmentation

Cloud deployment with user authentication

👨‍💻 Author
Harsha
AI & Machine Learning Enthusiast
GitHub: https://github.com/Harsha-2005
LinkedIn: https://www.linkedin.com/in/harsha-pavan-maddala/
