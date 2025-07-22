🚀 StockSage AI: Autonomous Financial Insight Crew
📘 Overview
StockSage AI is an autonomous, multi-agent system built using the CrewAI framework. This project automates end-to-end stock analysis and investment recommendations by orchestrating multiple AI agents, each with their own roles and expertise.

It supports:

Large Language Models (like GPT-4 or GPT-3.5)

Local models (like OpenHermes via Ollama)

Tools for scraping, searching, calculations, and SEC filings

By @joaomdmoura

🧠 How It Works (CrewAI Framework)
CrewAI allows AI agents to collaborate like a real team. In this project:

Each agent plays a different financial role.

They work together to analyze a stock and generate a detailed report with recommendations.

🚀 Getting Started
1. Setup Environment
Copy the .env.example file and add your API keys for:

OpenAI

Browserless

Serper

SEC-API

2. Install Dependencies
bash
Copy
Edit
poetry install --no-root
3. Run the App
bash
Copy
Edit
python main.py
👉 When prompted, enter the company name you want to analyze.

⚠️ Note: GPT-4 is used by default. API usage may incur costs unless you switch to a free/local model.

🔍 File Structure
File/Folder	Description
main.py	Main execution script
stock_analysis_agents.py	Defines AI agents
stock_analysis_tasks.py	Defines tasks for the agents
tools/	Custom tools for scraping, searching, calculating, etc.

🧠 Switching to GPT-3.5
You can change an agent’s LLM like this:

python
Copy
Edit
from langchain.chat_models import ChatOpenAI

llm = ChatOpenAI(model='gpt-3.5')  # Use GPT-3.5

Agent(
  role="The Best Financial Analyst",
  llm=llm,
  tools=[...]
)
🖥️ Using Local Models with Ollama
🔧 Setup
Install Ollama.

Tune with Modelfile settings if needed (add stop words like Observation, adjust top_p, temperature, etc.)

🧩 Integration Example:
python
Copy
Edit
from langchain.llms import Ollama
ollama_openhermes = Ollama(model="openhermes")

Agent(
  role="The Best Financial Analyst",
  llm=ollama_openhermes,
  tools=[...]
)
✅ Benefits of Local Models
Data Privacy 🔐

Custom Fine-tuning 🎯

Potential Cost & Latency Savings ⚡

🤝 Contributing
Contributions, feature requests, and improvements are welcome!

📬 Support
For questions or collaboration, feel free to reach out to the original author: @joaomdmoura

📝 License
This project is licensed under the MIT License.
