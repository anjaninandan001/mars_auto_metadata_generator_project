# 📄 Automated Metadata Generator

This project is a full-stack web application for **automated metadata generation** from unstructured documents like PDFs, DOCX, and scanned files. It combines **OCR**, **text extraction**, and **lightweight AI/NLP models** to generate structured metadata that enhances document discoverability and analysis.

---

## 🚀 Features

- ✅ Upload documents via a simple web UI
- 📤 Supports PDF, DOCX, and TXT formats (OCR for scanned files)
- 🧠 Extracts semantically rich content (title, summary, tags, etc.)
- 🗃️ Generates structured metadata (JSON-based)
- 🌐 Flask-powered web app with a clean interface
- ☁️ Deployable on Render, Railway, or local IP
- 📦 Lightweight and cost-efficient (supports Gemma 1B or local LLM)

---

## 📁 Project Structure

```bash
automated-metadata-generator/
│
├── app.py                            # Flask backend for file upload + metadata
├── requirements.txt                  # Include OpenAI/HuggingFace/etc.
├── README.md                         # Project explanation
│
├── metadata/                       
│   ├── __init__.py
│   ├── text_extractor.py             # Extract text from files (PDF, DOCX, OCR)
│   ├── metadata_generator.py         # this is only include in ipynb file as of now it is blanked.
│   └── llm_generator.py              # use LLMs to refine metadata
│
├── templates/                        # Web interface (HTML)
│   ├── upload.html
│   └── result.html
│
├── static/                           
│   └── style.css                     # UI styling
│
├── uploads/                          # Temporarily stores uploaded files
└── .env                              # API keys and environment variables

## ⚙️ How It Works

1. **User uploads a document** via the interface.
2. **Text extraction** happens via `text_extractor.py` using:
   - **PyMuPDF** for PDFs
   - **python-docx** for Word files
   - **Tesseract OCR** for scanned/image-based documents
3. **Metadata is generated** using a combination of rule-based and model-based logic (LLMs optional).
4. **Metadata is displayed** in a clean HTML view (`result.html`).

---

## 🧪 Technologies Used

- Python, Flask  
- PyMuPDF, python-docx, pytesseract  
- JSON, HTML, CSS  
- Lightweight LLMs like **Gemma 1B or Mistral**   
- Deployment via **Render** or **local IP**

---

## 🧰 Setup Instructions

### 🔧 Prerequisites

- Python 3.9+
- `tesseract-ocr` installed and in system PATH (for OCR)
- Required Python packages from `requirements.txt`

### ▶️ Run Locally

```bash
git clone https://github.com/your-username/automated-metadata-generator.git
cd automated-metadata-generator

# Create virtual environment
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt

# Run the Flask app
python app.py


## Project Link
- 🌐 **Live Deployed Web App:** [Try it here](https://metagenerator-5.onrender.com/)  
- 🎥 **Demo Video (2 min):** [Watch](https://drive.google.com/file/d/1XTtJrOJb1KYVVUL8K2RgfjjQT_Ofh169/view?usp=sharing)
