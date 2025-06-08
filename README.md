# MCP Project

This project demonstrates the use of the Model Context Protocol (MCP) with a chatbot that can interact with tools defined in a separate server.

## Files

- **[research_server.py](research_server.py)**: This script defines an MCP server with tools for searching and extracting information about research papers from arXiv.
- **[mcp_chatbot.py](mcp_chatbot.py)**: This script implements a chatbot that connects to the `research_server.py` using MCP. It allows users to query the chatbot, which can then utilize the tools provided by the server.
- **[chatbot_using_tools.py](chatbot_using_tools.py)**: This script is a standalone chatbot that directly implements and uses the paper searching and information extraction functionalities without relying on MCP or a separate server.

## Running the Code

### 1. Running the Research Server

The `research_server.py` provides tools that the `mcp_chatbot.py` can use. To run the server with the MCP inspector:

```sh
npx @modelcontextprotocol/inspector uv run research_server.py
```

Alternatively, you can run it as a standard Python script if you don't need the inspector:
```sh
python research_server.py
```

### 2. Running the MCP Chatbot

Once the `research_server.py` is running, you can start the `mcp_chatbot.py` in a separate terminal:

```sh
python mcp_chatbot.py
```
This chatbot will connect to the running `research_server.py` and allow you to interact with its tools through a chat interface.

### 3. Running the Standalone Chatbot

The `chatbot_using_tools.py` can be run independently:

```sh
python chatbot_using_tools.py
```
This script includes the tool implementations directly and does not require the `research_server.py` to be running.

## Environment Variables
Ensure you have a [.env](.env) file in the root directory with your `ANTHROPIC_API_KEY`:
```
ANTHROPIC_API_KEY="your_api_key_here"
```
