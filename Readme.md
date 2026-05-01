# MCP Multi-Agent Trading System

An MCP-based multi-agent system that orchestrates specialized agents for stock selection, market data analysis, news sentiment, and trading recommendations using LangGraph.

---

## Overview

This project demonstrates how to build a **multi-agent AI system** using the Model Context Protocol (MCP) and LangGraph.

It simulates a real-world trading workflow by coordinating multiple agents, each responsible for a specific task:

- Stock discovery
- Market data analysis
- News sentiment analysis
- Trading decision recommendations

A supervisor agent manages the workflow and ensures tasks are executed sequentially.

---

## Architecture

The system consists of the following agents:

### 1. Stock Finder Agent
Identifies 2 promising NSE-listed stocks, avoids illiquid and penny stocks, and uses recent performance and trends.

### 2. Market Data Agent
Fetches current price, volume, price trends (7-day, 30-day), and technical indicators (RSI, moving averages).

### 3. News Analyst Agent
Retrieves recent news (last 3–5 days), performs sentiment analysis (positive / negative / neutral), and evaluates short-term impact.

### 4. Price Recommender Agent
Suggests a Buy / Sell / Hold decision and target price based on combined data and sentiment.

### 5. Supervisor Agent
Orchestrates all agents, assigns tasks step-by-step (no parallel execution), and ensures full workflow completion.

---

## Tech Stack

- Python
- LangChain
- LangGraph
- MCP (Model Context Protocol)
- OpenAI GPT models
- Bright Data MCP tools

---

## Project Structure

```
.
├── main.py                 # Simple MCP agent example (flight search)
├── multi_agent_demo.py     # Full multi-agent trading system
├── .env                    # Environment variables
└── README.md
```

---

## Setup

### 1. Clone the Repository

```bash
git clone https://github.com/your-username/mcp-multi-agent-trader.git
cd mcp-multi-agent-trader
```

### 2. Install Dependencies

```bash
pip install -r requirements.txt
```

### 3. Set Environment Variables

Create a `.env` file:

```env
OPENAI_API_KEY=your_openai_api_key
BRIGHT_DATA_API_TOKEN=your_brightdata_token
WEB_UNLOCKER_ZONE=unblocker
BROWSER_ZONE=scraping_browser
```

---

## Usage

### Run the Multi-Agent System

```bash
python multi_agent_demo.py
```

Example query:

```
Give me good stock recommendation from NSE
```

### Run Basic MCP Agent (Optional)

```bash
python main.py
```

Example query:

```
Find flights from Bangalore to Delhi
```

---

## Workflow

1. Supervisor receives user query
2. Calls **Stock Finder Agent**
3. Passes results to **Market Data Agent**
4. Sends enriched data to **News Analyst Agent**
5. Final decision made by **Price Recommender Agent**
6. Returns structured trading insights

---

## Features

- Multi-agent orchestration using LangGraph
- Real-time data access via MCP tools
- Modular and extensible agent design
- Sequential task execution with supervisor control
- Combines quantitative and qualitative analysis

---

## Example Output

```
Stock: RELIANCE
Recommendation: BUY
Target Price: ₹2500
Reason: Positive news sentiment + strong upward trend + high volume

Stock: INFY
Recommendation: HOLD
Target Price: ₹1500
Reason: Neutral news + stable trend
```

---

## Future Improvements

- Add more technical indicators
- Support global markets (NASDAQ, NYSE)
- Real-time streaming data
- UI dashboard for visualization
- Backtesting module

---

## Contributing

Contributions are welcome!

1. Fork the repo
2. Create a new branch
3. Submit a PR

---

## License

This project is licensed under the MIT License.

---

> **Note:** This project is for educational and experimental purposes only. Not financial advice.
