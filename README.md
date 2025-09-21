# Sidekick Personal Co-Worker 🤖

Sidekick is a Python-based assistant application designed to help users complete tasks by leveraging a variety of tools, including web browsing, file management, web searches, and push notifications. Built with a modular architecture using LangGraph, it orchestrates task execution through a stateful workflow, ensuring tasks meet user-defined success criteria. The application features a Gradio-based web interface for interactive user engagement.

## Features ✨
- **Task Automation**: Executes tasks using tools like Playwright for web browsing, Google Serper for searches, Wikipedia queries, and Python code execution.
- **Stateful Workflow**: Uses LangGraph to manage task states, ensuring tasks progress until success criteria are met or user input is needed.
- **Interactive Interface**: Provides a Gradio-based UI for users to input tasks, define success criteria, and view conversation history.
- **Feedback Loop**: Includes an evaluator to assess task completion and provide feedback, allowing iterative task refinement.
- **Push Notifications**: Sends notifications via Pushover for task updates.
- **File Management**: Supports file operations within a sandboxed directory.

## Project Structure 📁
- **`sidekick.py`**: Core logic for the Sidekick assistant, defining the state graph, worker, and evaluator nodes for task execution and assessment.
- **`sidekick_tools.py`**: Provides tools for web browsing (Playwright), file management, web searches (Google Serper), Wikipedia queries, Python code execution, and push notifications (Pushover).
- **`app.py`**: Implements the Gradio-based web interface for user interaction, handling task submission and state management.
- **`sandbox/`**: Directory for file management operations, used by the FileManagementToolkit.

## Installation 🛠️
1. Clone the repository:
   ```bash
   git clone https://github.com/aidoanto123/SideKick-App.git
   cd SideKick-App

2. `Install dependencies`
  ~~~bash
  pip install -r requirements.txt
  ~~~

3. `Set environment variables`
  Create a `.env` file in the project root:
  ~~~env
  OPENAI_API_KEY=<your-openai-api-key>
  PUSHOVER_TOKEN=<your-pushover-token>
  PUSHOVER_USER=<your-pushover-user>
  SERPER_API_KEY=<your-serper-api-key>
  ~~~


# `▶️ Usage`

### `Launch the application`
~~~bash
python app.py
~~~

1. **`Launch the application`** to open the Gradio interface in your browser.
2. **`Enter your task request`** in the textbox (e.g., "Find recent articles on AI advancements").
3. **`Specify success criteria`** (e.g., "Provide a summary of at least three articles published in 2025").
4. **`Click Go or Reset`** Click "Go!" to process the task or "Reset" to clear the session.
5. **`View conversation history`** and evaluator feedback in the chat interface.

---

## Requirements 📋
- **`Python`**: 3.8+
- **`Libraries`**:
  - gradio
  - langchain
  - langchain-openai
  - langgraph
  - playwright
  - python-dotenv
  - requests
  - pydantic
  - langchain-community
  - langchain-experimental
- **`API Keys`**:
  - OpenAI
  - Google Serper
  - Pushover

---

## Notes 📝
- **`Browser Usage`**: The application uses a headless Chromium browser via Playwright for web navigation. Ensure sufficient system resources for browser operations.
- **`Python REPL`**: The Python REPL tool requires `print()` statements to capture output.
- **`Dynamic Date and Time`**: The current date and time are dynamically included in task prompts for context-aware responses.
- **`Sandboxed Environment`**: The application runs in a sandboxed environment for file operations to ensure security.
