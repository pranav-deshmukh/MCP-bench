# 🛠️ MCP-Workbench (Multi-LLM Client)

> The integrated environment to Debug, Benchmark, and Evaluate your Model Context Protocol (MCP) servers.

**MCP-Workbench** is an open-source interface that lets you plug in any MCP server, chat with it using multiple models (Claude, GPT-4, etc.), and **run statistical evaluations** on tool performance.

## 🚨 The Problem

Building **Model Context Protocol (MCP)** servers is the easy part. Debugging them is hard.

When your LLM fails to use a tool correctly, is it because:
1. The model is not capable enough?
2. The tool description is vague?
3. The JSON schema is malformed?

MCP-Workbench helps you answer these questions by providing a unified environment for testing and evaluation.

## ✨ Key Features

### 🔌 Universal MCP Inspector
Connect any local or remote MCP server (Filesystem, Brave Search, Postgres, etc.) directly to the web client.
- **Tool Discovery:** Auto-detects available tools and resources.
- **Interactive Chat:** Test tools manually in a chat interface to verify logic.

### 📊 Eval-Stats Dashboard
*Switch to the `eval-stats` branch to access this feature.*
Stop guessing. Run evaluation datasets against your connected MCP tools.
- **Success Rate Tracking:** See how often the model successfully calls the tool vs. failing.
- **Performance Metrics:** Track latency and execution reliability for your tools.
- **Data-Driven Optimization:** Use the stats to refine your tool descriptions and schemas.

### ⚔️ Multi-Model Support
Compare how different models handle your tools.
- Does `gpt-4o` handle your complex schema better than `claude-3-5-sonnet`?
- Switch models instantly to verify cross-model compatibility.

## 🤖 Supported Models

MCP-Workbench supports a variety of LLM providers out of the box:

- **OpenAI:** GPT-4o, GPT-4 Turbo, GPT-3.5 Turbo
- **Anthropic:** Claude 3.5 Sonnet, Claude 3 Opus, Claude 3 Haiku
- **Google:** Gemini 2.5 Flash
- **Alibaba:** Qwen2.5-Max, Qwen Turbo, Qwen Plus

## 🛠️ Tech Stack

- **Framework:** Next.js 14 (App Router)
- **Language:** TypeScript
- **Styling:** Tailwind CSS
- **Database:** MongoDB (for chat history and evaluation logs)
- **AI Integration:** Vercel AI SDK for multi-provider support.

## 🚀 Getting Started

### Prerequisites

- Node.js >= 18.x
- pnpm

### Installation

1.  **Clone the repository:**
    ```bash
    git clone https://github.com/pranav-deshmukh/MCP-bench.git
    cd MCP-bench
    ```

2.  **Install dependencies:**
    ```bash
    pnpm install
    ```

3.  **Set up environment variables:**

    Create a `.env.local` file in the root of the project by copying the example file:
    ```bash
    cp .env.example .env.local
    ```

    Then, fill in the required API keys and secrets in `.env.local`:

    ```bash
    # MongoDB Connection String
    MONGO_URI=your_mongodb_connection_string

    # AI Provider API Keys
    ANTHROPIC_API_KEY=your_anthropic_api_key
    OPENAI_API_KEY=your_openai_api_key
    GOOGLE_API_KEY=your_google_api_key

    # API keys for specific MCP servers (if you use them)
    FIGMA_API_KEY=
    NEXT_PUBLIC_GITHUB_PERSONAL_ACCESS_TOKEN=
    NEXT_PUBLIC_NOTION_TOKEN=
    ```

### Running the Application

1.  **Start the development server:**
    ```bash
    pnpm dev
    ```

2.  **Open the application:**
    Open [http://localhost:3000](http://localhost:3000) in your browser to see the result.

## 🐳 Docker

You can also run the application using Docker for a more isolated environment.

1.  **Build and run the container:**
    ```bash
    docker-compose up -d --build
    ```
    *Make sure your `.env.local` file is created before running this command, as Docker Compose will use it.*

2.  **Access the application:**
    It will be available at [http://localhost:3000](http://localhost:3000).

## 🤝 Contributing

Contributions are welcome! Please feel free to open an issue or submit a pull request if you have any ideas for improvement.

## 📄 License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

