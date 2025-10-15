# Agentic AI Financial Analysis System

### Final Project – Advanced AI Program (AAI)
**Team Members:** Laxminag Mamillapalli, Sunil Prasath
**Group:** No 13 AAI-520


## Project Overview

This project implements a **real-world financial analysis system powered by Agentic AI**.  
Unlike traditional NLP or automation pipelines, our system uses **multiple coordinated agents** that can reason, plan, and act autonomously.  

Each agent dynamically uses tools (APIs, datasets, retrieval systems), self-reflects on its outputs, and iteratively improves performance — simulating how **modern financial research teams** use intelligent systems to monitor markets, parse news, and generate actionable insights.



## Objectives

- Build an **autonomous Investment Research Agent** that:
  - Plans its research workflow for a given stock symbol  
  - Retrieves and analyzes real-time financial data  
  - Processes and classifies financial news  
  - Evaluates the quality of its own analysis  
  - Learns iteratively across runs through a simple memory store  

- Implement **three key Agentic AI workflow patterns**:
  1. **Prompt Chaining:** News → Preprocess → Classify → Extract → Summarize  
  2. **Routing:** Send content to specialized agents (earnings, macro, sentiment)  
  3. **Evaluator–Optimizer:** Generate → Evaluate → Refine → Improve  



## Architecture

```
 ┌────────────────────────────┐
 │ Investment Research Agent  │
 │   ├── Planner              │
 │   ├── Tool Manager         │
 │   ├── Evaluator            │
 │   ├── Memory Store         │
 └────────────────────────────┘
          │
          ▼
 ┌───────────────────────────────────────────────────────────┐
 │  Prompt Chain: News → Preprocess → Classify → Summarize   │
 └───────────────────────────────────────────────────────────┘
          │
          ▼
 ┌────────────────────────────────────────────┐
 │ Routing Layer: Earnings / Macro / News     │
 └────────────────────────────────────────────┘
          │
          ▼
 ┌────────────────────────────┐
 │ Evaluator–Optimizer Loop   │
 └────────────────────────────┘
```



## Tech Stack

| Category | Tools & Libraries |
|-----------|------------------|
| **Core** | Python, Pandas, NumPy, Requests |
| **Agentic Framework** | LangChain, LangGraph, OpenAI API |
| **Finance APIs** | Yahoo Finance (`yfinance`), NewsAPI, FRED, Alpha Vantage |
| **Data Storage** | Local JSON / SQLite memory |
| **Visualization** | Matplotlib, Plotly |
| **Version Control** | GitHub (Team Repository) |
| **Code Quality** | Black, Ruff, Mypy |
| **Notebook Export** | Jupyter, nbconvert, Pyppeteer |



## Description of Agent Workings

1. **Input:**  
   User provides a stock symbol (e.g., `AAPL`, `TSLA`).

2. **Planning:**  
   The Investment Agent decides which APIs and workflows to run.

3. **Data Retrieval:**  
   - Pulls stock data from Yahoo Finance  
   - Fetches relevant financial news from NewsAPI  
   - Optionally includes FRED macroeconomic indicators  

4. **Processing & Reasoning:**  
   - Uses Prompt Chaining to clean, classify, and summarize news  
   - Routes data to specialized analyzers (earnings, macro, sentiment)  

5. **Evaluation & Feedback:**  
   - Evaluator Agent critiques the analysis  
   - Optimizer Agent refines the output based on feedback  

6. **Output:**  
   - A concise AI-generated financial research report  
   - Example sections: **Summary**, **Sentiment Trend**, **Key Insights**, **Confidence Score**
