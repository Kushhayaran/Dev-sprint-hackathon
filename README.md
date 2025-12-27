# Dev-sprint-hackathon
hackathon project
🛡️ VIGILE: The Smart AI Chat Moderator
VIGILE is a real-time chat moderation layer designed to keep digital conversations safe, professional, and engaging. Built for the MANTHAN 1.0 hackathon, it acts as an intelligent middleware between users and chat interfaces, utilizing Google Gemini's advanced LLMs to detect toxicity and suggest polite alternatives instantly.

🚀 Key Features
Real-Time Toxicity Scoring: Evaluates every message on a granular 0–10 scale.

Hard-Gate Blocking: High-toxicity content is intercepted and rejected before it ever reaches the chat history.

Graduated Warnings: Low-level toxicity triggers a behavioral warning, coaching users to maintain a positive community tone.

Polite Rephrasing: Instead of simple redaction, VIGILE provides AI-generated professional suggestions to help users communicate better.

Admin Dashboard: A live moderation feed in the sidebar for real-time audit and oversight.

Model Fallback Architecture: Automatically cycles between Gemini 2.0 and 1.5 models to ensure 100% availability even during traffic spikes.

🛠️ Technical Stack
Frontend: Streamlit (Python-based Web UI).

AI Engine: Google Gemini API (Flash 2.0 & 1.5).

Environment Management: python-dotenv for secure API key handling.

Data Structure: JSON-based communication with LLM for reliable scoring.

📂 Project Structure
Plaintext

vigile-moderator/
├── .streamlit/
│   └── secrets.toml     # (Optional) For Streamlit Cloud deployment
├── app.py               # Main application logic
├── .env                 # API Key storage (DO NOT COMMIT)
├── .gitignore           # Prevents sensitive files from being uploaded
└── requirements.txt     # List of Python dependencies
⚙️ Setup & Installation
Clone the Repository:

Bash

git clone https://github.com/yourusername/vigile-moderator.git
cd vigile-moderator
Install Dependencies:

Bash

pip install streamlit google-genai python-dotenv
Configure API Key: Create a .env file in the root directory and add your Google AI Studio API Key:

Plaintext

Gemini_api_key=your_api_key_here
Run the Application:

Bash

streamlit run app.py
📊 Architecture Flow
User Input: Captures message from the Streamlit UI.

AI Analysis: Single-call prompt scores the text and generates a reply.

Threshold Engine: Compares score against user-defined sliders (Blocking/Warning).

Action Controller: Decides whether to Deliver, Warn, or Reject.

Audit Log: Records the event in the sidebar Admin Feed.

🛡️ Moderation Philosophy
VIGILE follows the "Correction over Deletion" principle. By suggesting professional ways to express frustration, we de-escalate conflicts rather than just silencing voices.
