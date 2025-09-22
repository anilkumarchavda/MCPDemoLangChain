# MCP Demo with LangChain & LangGraph

This project demonstrates how to integrate **LangChain**, **LangGraph**, and **MCP (Model Context Protocol)** with custom math and weather servers.  
It sets up a simple agent capable of performing math calculations and retrieving weather information via MCP tools, powered by **Groq LLMs**.
 
---

## 📂 Project Structure

```
.
├── client.py          # Main async client using LangChain + MCP + Groq
├── main.py            # Entry point (prints Hello world)
├── mathserver.py      # MCP math server with add/multiply tools
├── weather.py         # MCP weather server (HTTP transport)
├── pyproject.toml     # Project metadata and dependencies
├── requirements.txt   # Minimal requirements file
├── uv.lock            # Lock file for dependencies
├── .gitignore
├── .python-version
```

---

## 🚀 Features

- **MCP Servers**
  - Math server with `add(a, b)` and `multiply(a, b)` tools.
  - Weather server with `get_weather(location)` tool.
- **LangChain + LangGraph Agent**
  - Uses `create_react_agent` to dynamically select and invoke MCP tools.
- **Groq Integration**
  - Powered by **ChatGroq** (`qwen/qwen3-32b` model) for reasoning and orchestration.

---

## 🛠️ Installation

### 1. Clone the Repository
```bash
git clone https://github.com/your-username/mcpdemolangchain.git
cd mcpdemolangchain
```

### 2. Create Virtual Environment (Python 3.13+)
```bash
python -m venv .venv
.venv\Scripts\activate   # On Windows
```

### 3. Install Dependencies
```bash
pip install -r requirements.txt
```

Or, if using `uv`:
```bash
uv sync
```

---

## ⚙️ Configuration

Set your **Groq API key** in a `.env` file:

```ini
GROQ_API_KEY=your_api_key_here
```

---

## ▶️ Usage

### 1. Start Math Server
```bash
python mathserver.py
```

### 2. Start Weather Server
```bash
python weather.py
```

### 3. Run Client
```bash
python client.py
```

Expected output:
```
Math response: 96
Weather response: Its always raining in california
```

---

## 📦 Dependencies

- [LangChain-Groq](https://pypi.org/project/langchain-groq/)
- [LangChain-MCP-Adapters](https://pypi.org/project/langchain-mcp-adapters/)
- [LangGraph](https://pypi.org/project/langgraph/)
- [MCP](https://pypi.org/project/mcp/)

---

## 🧪 Example Queries

The agent can answer:
- Math:  
  *User*: “What’s (3 + 5) × 12?” → *Response*: `96`  
- Weather:  
  *User*: “What is the weather in California?” → *Response*: `"Its always raining in california"`

---

## 📜 License

MIT License. See [LICENSE](LICENSE) for details.
