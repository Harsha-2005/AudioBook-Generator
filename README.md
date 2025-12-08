# 🎧 AI AudioBook Generator

[![Python Version](https://img.shields.io/badge/Python-3.11-blue?logo=python&logoColor=white)](https://www.python.org/)
[![Streamlit App](https://img.shields.io/badge/Streamlit-UI-red?logo=streamlit&logoColor=white)](https://your-app.streamlit.app/)
[![Gemini-LLM](https://img.shields.io/badge/Gemini-LLM-yellow?logo=google&logoColor=white)](https://gemini.google.com/app?hl=en-IN)
[![Coqui TTS](https://img.shields.io/badge/Coqui-TTS-green?logo=coqui&logoColor=white)](https://coquitts.com/)
[![License](https://img.shields.io/badge/License-MIT-green)](LICENSE)

The AI AudioBook Generator is an advanced application that transforms text documents into expressive, human-like audiobooks. It extracts text from various file formats, rewrites it in a storytelling style using Gemini LLM, and converts it into natural speech using Coqui TTS or pyttsx3.

## ✨ Features

- 📄 **Multi-Format Support**: Upload PDF, DOCX, and TXT documents
- 🤖 **AI-Powered Narration**: Gemini LLM enhances text into audiobook-style narration
- 🎙️ **Natural Speech Generation**: Coqui TTS for high-quality voice synthesis
- 📴 **Offline Capability**: pyttsx3 fallback for offline usage
- 🔒 **Secure Configuration**: Environment-based API key management
- 🎨 **User-Friendly UI**: Clean, interactive Streamlit interface
- ⚙️ **Centralized Configuration**: Easy settings management via `config.py`

## 🎯 Target Audience

- **Students** for learning on the go
- **Professionals** for consuming reports and documents
- **Visually impaired users** for accessible content
- **Content creators** for repurposing written content
- **Anyone** who prefers listening over reading

## 🏗️ System Architecture

```
AI-AudioBook-Generator/
│
├── app.py                    # Streamlit user interface
├── config.py                 # Loads .env and manages global settings
├── llm_enrichment.py         # Gemini AI narration enhancement
├── text_extraction.py        # PDF/DOCX/TXT text extraction
├── tts_generator.py          # Coqui TTS + pyttsx3 audio generation
├── requirements.txt          # Python dependencies
├── .env.example              # Environment variables template
└── README.md                 # Project documentation
```

## 📋 Prerequisites

- Python 3.11 or higher
- Git
- Internet connection (for Gemini API and Coqui TTS)
- API keys for Gemini AI

## 🚀 Quick Installation

### 1️⃣ Clone the Repository
```bash
git clone https://github.com/Harsha-2005/AI-AudioBook-Generator.git
cd AI-AudioBook-Generator
```

### 2️⃣ Create Virtual Environment
```bash
# Windows
python -m venv venv
venv\Scripts\activate

# macOS/Linux
python -m venv venv
source venv/bin/activate
```

### 3️⃣ Install Dependencies
```bash
pip install -r requirements.txt
```

### 4️⃣ System Dependencies

**Windows:**
- Install [eSpeak NG](https://github.com/espeak-ng/espeak-ng)
- Add it to PATH
- Restart terminal

**Ubuntu/Linux:**
```bash
sudo apt update
sudo apt install espeak-ng
```

**macOS:**
```bash
brew install espeak
```

## 🔐 Configuration

### 1. Get API Keys
1. Visit [Google AI Studio](https://makersuite.google.com/app/apikey)
2. Generate a Gemini API key
3. (Optional) Get OpenAI API key if needed

### 2. Configure Environment
Create a `.env` file in the project root:

```env
# API Keys
GEMINI_API_KEY=your_gemini_api_key_here
OPENAI_API_KEY=your_openai_api_key_here

# TTS Configuration
TTS_ENGINE=coqui
TTS_OUTPUT_FORMAT=wav

# Application Settings
DEBUG_MODE=False
```

⚠️ **Important**: Add `.env` to `.gitignore` to keep your keys secure!

## 🖥️ Usage

### Start the Application
```bash
streamlit run app.py
```

### Using the Web Interface

1. **Upload Document**: Drag and drop or select a PDF, DOCX, or TXT file
2. **Preview Text**: Review the extracted text before processing
3. **Generate Audiobook**: Click the "Generate Audiobook" button
4. **Listen/Download**: Play the audio directly or download the generated file

### Workflow
```
Upload Document → Extract Text → AI Narration Enhancement → Convert to Speech → Download Audiobook
```

## 🧠 How It Works

### 1. Text Extraction
- **PDF**: Uses PyPDF2 & pdfplumber for accurate text extraction
- **DOCX**: Leverages python-docx for Word document parsing
- **TXT**: Direct file reading with encoding detection

### 2. AI Narration Enhancement
- Gemini LLM rewrites text into audiobook-style narration
- Intelligent chunking prevents token overflow
- Adds expressive elements for better listening experience

### 3. Text-to-Speech Generation
- **Primary**: Coqui TTS for natural, human-like speech
- **Fallback**: pyttsx3 for offline functionality
- Configurable output formats (WAV, MP3)

### 4. User Interface
- Streamlit-based interactive UI
- Real-time progress tracking
- Audio playback and download options

## 🧪 Testing

### Unit Testing
```bash
python -m pytest tests/
```

### Test Coverage
- ✅ Text extraction from all supported formats
- ✅ LLM narration enhancement
- ✅ Audio synthesis with both TTS engines
- ✅ Error handling and fallback mechanisms

## 🚀 Deployment Options

### Option 1: Streamlit Cloud
1. Push code to GitHub
2. Connect to [Streamlit Cloud](https://streamlit.io/cloud)
3. Add environment variables in settings

### Option 2: Hugging Face Spaces
1. Create new Space
2. Select Streamlit SDK
3. Upload code and configure secrets

### Option 3: Docker
```bash
# Build Docker image
docker build -t audiobook-generator .

# Run container
docker run -p 8501:8501 audiobook-generator
```

### Option 4: Local Deployment
```bash
# Run as background service
nohup streamlit run app.py --server.port 8501 &
```

## 🧰 Tech Stack

| Category               | Technology                  |
|------------------------|----------------------------|
| **Programming Language** | Python 3.11              |
| **UI Framework**       | Streamlit                  |
| **AI/ML**              | Google Gemini LLM          |
| **Speech Synthesis**   | Coqui TTS, pyttsx3         |
| **Text Extraction**    | PyPDF2, pdfplumber, python-docx |
| **Configuration**      | python-dotenv              |
| **Document Parsing**   | PyMuPDF, docx2txt          |

## 🔧 Troubleshooting

### Common Issues

1. **API Key Errors**
   - Verify `.env` file exists and contains correct keys
   - Check API key validity at Google AI Studio

2. **TTS Engine Issues**
   - Ensure eSpeak NG is properly installed
   - Check internet connection for Coqui TTS

3. **Memory Issues**
   - Reduce chunk size in `config.py` for large documents
   - Close other applications to free up memory

### Logs
Enable debug mode in `.env` for detailed logging:
```env
DEBUG_MODE=True
```

## 📈 Performance Metrics

| Document Size | Processing Time | Audio Duration |
|---------------|-----------------|----------------|
| 1-10 pages    | 1-2 minutes     | 5-15 minutes   |
| 10-50 pages   | 3-5 minutes     | 15-60 minutes  |
| 50+ pages     | 5-10+ minutes   | 60+ minutes    |

## 🔮 Future Enhancements

- 🎭 **Multi-voice selection** for different characters
- 🌍 **Multi-language support** for global accessibility
- 🎵 **Background music mixing** options
- 📖 **Chapter-wise audio segmentation**
- ☁️ **Cloud storage integration** for saving audiobooks
- 👥 **User authentication** and library management
- 📱 **Mobile app** development
- 🔍 **OCR support** for scanned documents

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- [Google Gemini AI](https://deepmind.google/technologies/gemini/)
- [Coqui TTS](https://github.com/coqui-ai/TTS)
- [Streamlit](https://streamlit.io/)
- All open-source libraries used in this project

## 👨‍💻 Author

**Harsha Pavan Maddala**
- GitHub: [@Harsha-2005](https://github.com/Harsha-2005)
- LinkedIn: [Harsha Pavan Maddala](https://www.linkedin.com/in/harsha-pavan-maddala/)

