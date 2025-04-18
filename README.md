# Virtual-Telecaller

## Overview  
An AI-powered virtual telecaller system that integrates **real-time voice calls** with **natural, intelligent responses**. The system transcribes speech using voice recognition, processes it through a fine-tuned **LLM (Meta-Llama 3.2B-Instruct)**, and responds via text-to-speech for seamless, human-like interaction.

---

## 🚀 Features  
- Real-time voice calling with **Zego Express SDK**  
- **Speech-to-text** transcription  
- AI responses using fine-tuned **Llama-3.2B-Instruct** on the *Bitext-media-llm-chatbot-training-dataset*  
- **Text-to-speech** response delivery  
- Alternative **interactive chat interface**

---

## 🏗️ Architecture  
- **Frontend**: React.js app with voice & chat UI  
- **Backend**: Flask server for API and file operations  
- **Model Hosting**: Kaggle notebook running the fine-tuned Llama model  
- **Data Bridge**: Google Drive for file exchange (used due to limited compute resources)

---

## 🔄 Workflow  
1. User starts a voice call via frontend  
2. Speech is transcribed into text  
3. Text is sent to Flask backend  
4. Text is uploaded to Google Drive  
5. Kaggle notebook retrieves and processes it via LLM  
6. AI response is saved back to Drive  
7. Backend fetches response  
8. Frontend displays and reads it aloud  
9. Optional: Use chatbot UI for typed queries

---

## 🧪 Fine-Tuning Overview  
The **Meta-Llama-3.2-3B-Instruct** model was optimized through:

- 🧩 Transfer Learning with **LoRA**  
- ⚡ Model **Quantization** for speed & size reduction  
- 📋 Instruction Tuning for improved responses  
- 🔠 Advanced **Tokenization**  
- 🚀 **Accelerated training** with GPU/TPU & Flash Attention  
- 📊 Tracking via **WandB** or **TensorBoard**  
- ⚙️ Inference optimization for real-time performance

---

## 🛠️ Tech Stack  
- ⚛️ React.js  
- 📞 Zego Express Engine (WebRTC)  
- 🐍 Flask + CORS  
- ☁️ Google Drive API  
- 🧠 Meta-Llama-3.2-3B-Instruct (fine-tuned)

---

## 📦 Prerequisites  
- Node.js & npm  
- Python 3.13.2  
- Google Drive API credentials  
- Zego API credentials

---

## ⚙️ Installation
```bash
# Clone repository
git clone [repository-url]
cd telecaller
```

# Frontend setup
```bash
cd frontend
npm install
```

# Backend setup
```bash
cd ../backend
pip install -r requirements.txt
```

### Configuration
1. Update Zego credentials in `ZegoCall.js`:
   ```bash
   const APP_ID = [your-app-id]
   const APP_SIGN = [your-app-sign]
   const TOKEN=[zego_call_token]
   ```

2. Configure Google Drive access in `final.py`:
   ```bash python
   SERVICE_ACCOUNT_FILE = 'path/to/credentials.json'
   YOUR_EMAIL = 'your-email@example.com'
   FOLDER_ID = 'your-drive-folder-id'
   ```

3. Set up model endpoints in `final.py`:
   ```bash python
   endpoint = "your-model-endpoint"
   token = "your-api-key"
   ```

### Running the Application
```bash
# Start backend
cd backend
python final.py
```

# Start frontend (in a new terminal)
```bash
cd frontend
npm run dev
npm start
```

## 💡Usage
1. Open the application in your browser
2. Click "Start Call" to begin a voice conversation
3. Speak naturally - your speech will be transcribed
4. The AI will process your query and respond both visually and audibly
5. Alternatively, use the chat interface by clicking "Open Chatbot"

## Future Improvements
- Direct API communication instead of Drive middleware with availabilty of more computational resources.
- Enhanced error handling and recovery
- User authentication and personalization
- Expanded training dataset for better responses

💬 Open to feedback, suggestions, and collaboration to enhance this project further.
