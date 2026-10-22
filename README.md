Gemini Q&A Chatbot

A simple, fast question-and-answer chatbot built with Streamlit, LangChain and Google Gemini. Type a question, and the app sends it through a LangChain prompt-and-model chain and displays the answer in the browser. Model name, temperature and response length are configurable, and runs can optionally be traced with LangSmith.

Features
Conversational Q&A powered by Google Gemini models
Clean, lightweight web interface built with Streamlit
LangChain chain: ChatPromptTemplate | ChatGoogleGenerativeAI | StrOutputParser
Adjustable generation settings: model, temperature and maximum output tokens
Secure configuration: API keys are loaded from a .env file, never hard-coded
Optional LangSmith tracing for debugging and monitoring

Tech Stack
Component	Technology
Interface	Streamlit
LLM framework	LangChain
Model provider	Google Gemini (langchain-google-genai)
Configuration	python-dotenv
Tracing (optional)	LangSmith
Language	Python 3.11+

.
├── app.py              # Streamlit app and LangChain chain
├── requirements.txt    # Python dependencies
├── .env                # API keys (not committed)
└── README.md



git clone https://github.com/<your-username>/<your-repo-name>.git
cd <your-repo-name>

python -m venv venv
# Windows
venv\Scripts\activate
# macOS / Linux
source venv/bin/activate

pip install -r requirements.txt

GOOGLE_API_KEY=your_google_api_key_here

# Optional: LangSmith tracing
LANGCHAIN_API_KEY=your_langsmith_api_key_here

streamlit run app.py

Then open http://localhost:8501 in your browser.

Usage
Choose the model and adjust temperature and max tokens if you want to change the style or length of answers.
Type your question in the input box.
Read the answer displayed below.

Temperature controls creativity: lower values give focused, consistent answers, and higher values give more varied ones. Max tokens limits the length of the response.

Requirements
streamlit
python-dotenv
langchain
langchain-core
langchain-google-genai
Notes
Use a Gemini model that is available on your API plan. Some models are not included in the free tier and return a 429 quota exceeded error. Check the current model list and free-tier availability in Google AI Studio before choosing one.
Never commit your .env file. Add it to .gitignore so your keys stay private.
Roadmap
Conversation history and multi-turn memory
Streaming responses
Document upload for Q&A over your own files
Deployment to Streamlit Community Cloud
License

Released under the MIT License. See LICENSE for details.
