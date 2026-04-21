# Agentic Stock Sentiment System (LangChain + Multi-Source Fusion)

## Overview

This project is a multi-agent financial intelligence system that analyzes stock sentiment using:

- News data
- Market price and technical indicators
- LLM-based reasoning via LangChain

It combines these signals to generate a BUY / SELL / HOLD decision.

---

## Key Features

- Multi-source data fusion (news + price)
- Sentiment analysis using LLMs
- Technical indicators (SMA, price trends)
- Decision fusion logic
- Modular LangChain architecture
- Runnable-based pipelines (modern LangChain API)

---

## Architecture

```

User Input (Stock)
↓
Orchestrator
↓
┌──────────────┬──────────────┐
News Tool     Price Tool
↓              ↓
Sentiment Chain   Indicators
↓              ↓
└──── Fusion Chain ────┘
↓
Final Decision

```

---

## Project Structure

```

agentic/
│
├── app/
│   ├── main.py
│   ├── langchain_app/
│   │   ├── tools.py
│   │   ├── chains.py
│   │   ├── orchestrator.py
│   │
│   ├── agents/
│   │   ├── news_agent.py
│   │   ├── price_agent.py
│   │
│   ├── utils/
│       ├── config.py
│
├── .env
├── requirements.txt
└── README.md

```

---

## Setup

### 1. Clone the repository

```

git clone <your-repo-url>
cd agentic

```

---

### 2. Create virtual environment

```

python -m venv .venv
.venv\Scripts\activate

```

---

### 3. Install dependencies

```

pip install -r requirements.txt

```

---

### 4. Configure environment variables

Create a `.env` file:

```

OPENROUTER_API_KEY=your_api_key_here

```

---

## Run the Project

Run from project root:

```

python -m app.main

```

---

## Example

Input:

```

TSLA

```

Output:

```

PRICE DATA:
{...}

SENTIMENT:
{...}

FINAL DECISION:
BUY / SELL / HOLD

```

---

## How It Works

### Data Collection
- News headlines are fetched from external sources
- Stock data is fetched using yfinance

### Sentiment Analysis
- Implemented using a LangChain pipeline:
  Prompt → LLM → Output Parser

### Technical Analysis
- Calculates:
  - 5-day SMA
  - 10-day SMA
  - Price trends
  - Volume

### Decision Fusion
- Combines sentiment and technical indicators
- Applies rule-based reasoning:
  - Bullish + price above SMA → BUY
  - Bearish + price below SMA → SELL
  - Otherwise → HOLD

---

## Tech Stack

- Python
- LangChain (Runnable API)
- OpenRouter (LLM access)
- yfinance
- python-dotenv

---

## Disclaimer

This project is for educational purposes only.

It is not financial advice and should not be used for real trading decisions.

---

## Future Improvements

- Add memory (vector database / RAG)
- Multi-agent collaboration (analyst, quant, risk agent)
- Async execution and parallel pipelines
- Langflow integration for visual orchestration
- Real-time streaming data
- Backtesting system

---

## Learning Outcomes

- Built a custom agentic AI system
- Understood LangChain Runnable architecture
- Implemented multi-source reasoning pipelines
- Handled real-world API failures and fallbacks

---

## Author

Aryaman Roy
