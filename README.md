# Financial-Intelligence-Agent-powered-by-MCP

AI-powered Financial Assistant built using the Model Context Protocol (MCP), Ollama, and Qwen 2.5.

This project demonstrates how Large Language Models can interact with external tools and resources through MCP to perform portfolio management, account analysis, and stock trading operations.

---

## Overview

MCP Portfolio Advisor is a local AI agent that connects to an MCP-based financial server and performs real-world account operations such as:

* Retrieving account information
* Reading portfolio resources
* Buying stocks
* Selling stocks
* Viewing holdings
* Generating AI-powered portfolio analysis

The project uses a local Ollama-hosted Qwen 2.5 model, enabling fully local execution without relying on cloud-based LLM APIs.

---

## Features

### MCP Tool Discovery

Dynamically discovers tools exposed by the MCP server.

```python
session.list_tools()
```

### MCP Tool Execution

Executes financial operations through MCP tools.

```python
session.call_tool(...)
```

Supported tools:

* get_balance
* get_holdings
* buy_shares
* sell_shares
* change_strategy

### MCP Resource Access

Reads account information through MCP resources.

```python
session.read_resource(...)
```

Example Resource:

```text
accounts://accounts_server/{name}
```

### AI-Powered Financial Analysis

Portfolio data retrieved through MCP is analyzed using Qwen 2.5 running locally via Ollama.

Capabilities include:

* Portfolio evaluation
* Risk assessment
* Investment recommendations
* Financial insights

### Local LLM Integration

Uses:

* Ollama
* Qwen 2.5

for fully local inference.

---

## Architecture

```text
┌─────────────────────┐
│    Ollama Qwen2.5   │
└──────────┬──────────┘
           │
           ▼
┌─────────────────────┐
│    MCP Client       │
└──────────┬──────────┘
           │
           ▼
┌─────────────────────┐
│ Accounts MCP Server │
└──────────┬──────────┘
           │
           ▼
┌─────────────────────┐
│   Account Logic     │
└──────────┬──────────┘
           │
           ▼
┌─────────────────────┐
│     Database        │
└─────────────────────┘
```

---

## Project Structure

```text
mcp-portfolio-advisor/
│
├── README.md
├── mcp.ipynb
│
├── accounts.py
├── accounts_server.py
├── accounts_client.py
├── market.py
├── database.py
│
├── requirements.txt
├── info.png
│
└── .gitignore
```

---

## MCP Concepts Implemented

### Tools

Used MCP tools for:

* Account balance retrieval
* Holdings retrieval
* Buying stocks
* Selling stocks
* Strategy updates

### Resources

Used MCP resources for:

* Reading complete account information
* Portfolio inspection
* Financial analysis

### Client Session

Implemented MCP communication using:

```python
ClientSession
```

### STDIO Transport

Connected to MCP servers using:

```python
stdio_client
```

---

## Example Workflow

### Step 1

Connect to the MCP Server.

### Step 2

Discover available tools.

```python
tools = await session.list_tools()
```

### Step 3

Execute MCP tools.

```python
await session.call_tool(...)
```

### Step 4

Read account resources.

```python
await session.read_resource(...)
```

### Step 5

Send retrieved data to Qwen 2.5.

### Step 6

Generate AI-powered financial recommendations.

---


## Technologies Used

### AI

* Ollama
* Qwen 2.5

### MCP

* Model Context Protocol
* MCP Python SDK

### Backend

* Python 3.10
* SQLite
* AsyncIO

### Financial Services

* Polygon API

---

## Key Learnings

Through this project I gained practical experience with:

* Model Context Protocol (MCP)
* MCP Tools
* MCP Resources
* Client-Server Architectures
* AI Tool Calling
* Local LLM Deployment
* Ollama Integration
* Financial Agent Development
* Portfolio Management Workflows

---

## Future Improvements

* Multi-account portfolio management
* Autonomous trading strategies
* Multi-agent financial workflows
* Real-time market monitoring
* Portfolio optimization recommendations
* Risk-adjusted investment planning

---

## Author

**Prateek Choudhary**

Exploring MCP-based AI agents, local LLM systems, and intelligent financial applications using Ollama and Qwen 2.5.
