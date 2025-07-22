# 🚀 StockSage AI: Autonomous Financial Insight Crew

## 📘 Overview

**StockSage AI** is an autonomous, multi-agent system built using the **CrewAI framework**. This project automates end-to-end **stock analysis and investment recommendations** by orchestrating multiple AI agents, each with their own roles and expertise.

It supports:
- Large Language Models (GPT-4 / GPT-3.5)
- Local models via Ollama (e.g., OpenHermes)
- Tools for scraping, searching, calculations, and SEC filings

> Built by (@AnisElahi](https://www.linkedin.com/in/anis-elahi-sk))

---

## 🧠 How It Works (CrewAI Framework)

CrewAI allows AI agents to **collaborate like a real-world team**. In this project:
- Each agent plays a different **financial analysis role**
- They work together to generate a full stock analysis report + recommendation

---

## 🚀 Getting Started

### 1. Setup Environment
Copy the `.env.example` file and configure it with your API keys:
- [OpenAI](https://platform.openai.com/api-keys)
- [Browserless](https://www.browserless.io/)
- [Serper](https://serper.dev/)
- [SEC-API](https://sec-api.io)

### 2. Install Dependencies
```bash
poetry install --no-root
````

### 3. Run the Script

```bash
python main.py
```

You will be prompted to enter a **company name** for analysis.

> ⚠️ **Note:** By default, GPT-4 is used which may consume paid API credits.

---

## 📁 Project Structure

| Path                       | Description                                                            |
| -------------------------- | ---------------------------------------------------------------------- |
| `main.py`                  | Main script to run the CrewAI analysis                                 |
| `stock_analysis_agents.py` | Defines the AI agents and their roles                                  |
| `stock_analysis_tasks.py`  | Defines tasks and responsibilities for agents                          |
| `tools/`                   | Contains utility tools like scraping, search, and financial data tools |

---

## 🧠 Switching to GPT-3.5

To use GPT-3.5 instead of GPT-4, simply change the LLM in `main.py`:

```python
from langchain.chat_models import ChatOpenAI

llm = ChatOpenAI(model='gpt-3.5')  # Use GPT-3.5

Agent(
  role="The Best Financial Analyst",
  llm=llm,
  tools=[...]
)
```

---

## 🖥️ Using Local Models with Ollama

### 🔧 Setup

1. Install [Ollama](https://ollama.com)
2. Customize with a [`Modelfile`](https://github.com/jmorganca/ollama/blob/main/docs/modelfile.md) if needed

   * You can add stop words like `Observation`
   * Adjust `top_p`, `temperature`, etc.

### 🧩 Integration Example

```python
from langchain.llms import Ollama
ollama_openhermes = Ollama(model="openhermes")

Agent(
  role="The Best Financial Analyst",
  llm=ollama_openhermes,
  tools=[...]
)
```

### ✅ Local Model Benefits

* 🔐 **Privacy** — process data on your own infrastructure
* ⚙️ **Customization** — tailor models for your use case
* ⚡ **Speed** — potentially faster inference with low latency

---

## 🤝 Contributing

Pull requests, feature ideas, and suggestions are always welcome!

---

## 📬 Support

For questions or collaborations, contact the creator on [X](https://x.com/joaomdmoura).

---

## 📝 License

Licensed under the **MIT License**.

```


Let me know if you want:
- Badges (e.g., Python version, License, etc.)
- A GitHub description
- A cool project logo or banner  
I'm ready, boss 😎
```
