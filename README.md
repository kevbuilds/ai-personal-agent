# AI-Powered Personal Website Agent

An intelligent chatbot that represents me on my personal website, built with OpenAI's GPT-4o-mini and Gradio. This agent can answer questions about my background, experience, and skills while actively engaging with potential clients and employers.

https://huggingface.co/kevinlearnsai

## 🎯 Project Overview

This project demonstrates my ability to build practical AI applications by creating an autonomous agent that:
- Answers questions about my professional background using RAG (Retrieval Augmented Generation)
- Engages visitors in natural conversations
- Automatically captures leads by collecting email addresses
- Records unanswered questions for continuous improvement
- Sends real-time notifications via Pushover API

## 🚀 Features

### Core Capabilities
- **AI-Powered Conversations**: Utilizes OpenAI's GPT-4o-mini to provide intelligent, context-aware responses
- **Document Processing**: Extracts and processes information from my LinkedIn profile (PDF format)
- **Tool Integration**: Implements function calling to execute actions like recording user details and logging questions
- **Real-Time Notifications**: Integrates Pushover API for instant alerts when users interact
- **Web Interface**: Clean, accessible chat interface powered by Gradio

### Technical Highlights
- **Function Calling**: Demonstrates advanced OpenAI API usage with custom tool definitions
- **RAG Implementation**: Combines structured data (summary) and unstructured data (LinkedIn PDF) for context
- **Conversational AI**: Multi-turn conversations with tool execution in a loop
- **Production-Ready**: Secure environment variable management with python-dotenv

## 🛠️ Technology Stack

- **Python 3.x**: Core programming language
- **OpenAI API**: GPT-4o-mini for natural language processing
- **Gradio**: Web interface framework
- **pypdf**: PDF text extraction
- **Pushover API**: Real-time push notifications
- **python-dotenv**: Environment variable management

## 📋 Prerequisites

- Python 3.8 or higher
- OpenAI API key
- Pushover account (optional, for notifications)

## ⚙️ Installation

1. Clone the repository:
```bash
git clone <your-repo-url>
cd agents/1_foundations
```

2. Install required packages:
```bash
pip install -r requirements.txt
```

3. Create a `.env` file in the project root:
```env
OPENAI_API_KEY=your_openai_api_key_here
PUSHOVER_TOKEN=your_pushover_token_here  # Optional
PUSHOVER_USER=your_pushover_user_here    # Optional
```

4. Add your personal information:
   - Place your LinkedIn profile PDF in `me/linkedin.pdf`
   - Create a `me/summary.txt` with your professional summary

## 🚦 Usage

Run the application:
```bash
python app.py
```

The Gradio interface will launch in your browser, allowing you to interact with the AI agent.

## 🏗️ Architecture

### Agent Workflow
```
User Message → System Prompt + Context → GPT-4o-mini → Tool Calls? 
                                              ↓
                                            Yes → Execute Tool → Continue Loop
                                              ↓
                                            No → Return Response
```

### Key Components

1. **Me Class**: Main agent class that manages conversation state and tool execution
2. **System Prompt**: Dynamically generated context from LinkedIn PDF and summary
3. **Tool Definitions**: JSON schemas for function calling (record_user_details, record_unknown_question)
4. **Chat Loop**: Handles multi-turn conversations with tool execution

## 🎨 Customization

To adapt this agent for your own use:

1. Replace `me/linkedin.pdf` with your LinkedIn profile
2. Update `me/summary.txt` with your professional summary
3. Modify the `self.name` variable in the `Me` class
4. Customize the system prompt in `system_prompt()` method
5. Add or modify tool functions as needed

## 🔒 Security

- All sensitive credentials are stored in environment variables
- No API keys or tokens are hardcoded
- `.env` file is excluded from version control via `.gitignore`

## 📊 Future Enhancements

- [ ] Add conversation history persistence
- [ ] Implement analytics dashboard
- [ ] Support multiple file formats (Word, Text, etc.)
- [ ] Add sentiment analysis for user interactions
- [ ] Deploy to cloud platform (AWS, GCP, or Azure)
- [ ] Add voice interaction capabilities
- [ ] Implement vector database for better RAG performance

## 💡 Key Learnings

This project demonstrates:
- **API Integration**: Working with multiple external APIs (OpenAI, Pushover)
- **Function Calling**: Advanced LLM capabilities with tool use
- **Document Processing**: Extracting and utilizing unstructured data
- **UX Design**: Creating user-friendly AI interfaces
- **Production Practices**: Secure credential management and error handling

## 📝 License

This project is open source and available under the MIT License.

## 👤 About Me

I'm Kevin Nguyen, a data engineer and analytics consultant pursuing a master's degree in Artificial Intelligence at the University of Texas. I'm passionate about building practical AI solutions that solve real-world problems.

*Built with ❤️ as part of my AI learning journey*
