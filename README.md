# Multimodal Personal Chef Agent

A secure, human-centric multimodal AI agent designed to act as a personal chef. The agent processes text inputs of ingredient lists or inspects uploaded photos of leftover food to dynamically discover, summarize, and draft verified recipe ideas using real-time web verification.

---

## Tech Stack

![Python](https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54)
![LangChain](https://img.shields.io/badge/LangChain-1C3C3A?style=for-the-badge&logo=chainlink&logoColor=white)
![LangGraph](https://img.shields.io/badge/LangGraph-2E6F40?style=for-the-badge&logo=git&logoColor=white)
![OpenAI](https://img.shields.io/badge/OpenAI-412991?style=for-the-badge&logo=openai&logoColor=white)
![NVIDIA](https://img.shields.io/badge/NVIDIA-76B900?style=for-the-badge&logo=nvidia&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-F37626?style=for-the-badge&logo=jupyter&logoColor=white)

---

## Core Capabilities & Features

* **Multimodal Vision Pipeline**: Utilizes vision language models to extract and identify ingredients from images of leftover food, noting physical details and documenting visual uncertainty.
* **Dynamic Web Verification**: Integrates a web search tool powered by Tavily to cross-reference identified ingredients against live recipe databases to guarantee authentic, actionable suggestions.
* **Stateful Interaction Memory**: Leverages an in-memory checkpointer context (`InMemorySaver`) to support seamless, stateful multi-turn human conversations and follow-up requests.
* **Human-Centric UX Controls**: Programmed to output concise recipe ideas first, completely withholding comprehensive step-by-step instructions until explicitly prompted by the user to avoid information overload.

---

## Project Architecture & Workflow

The architecture decouples the vision parsing from the search engine execution to optimize tool usage and prevent leaking raw binary image payloads to external search APIs:

1. **Vision Inference Pass**: The visual model (`nvidia/nemotron-nano-12b-v2-vl`) parses raw base64 image data to construct a clean, text-based manifest of detected ingredients without accessing the open web.
2. **Agentic Action Pass**: The primary agent coordinator (`openai/gpt-4o-mini`) ingests that ingredient manifest, determines the best search queries, and drives the Tavily search engine wrapper to retrieve contextual matching recipes.

---

## Multi-Turn Execution Implementations

The system is split into two distinct pipeline entry points depending on the user's input type:

### 1. Text-Only Pipeline
* **Input**: Direct raw text message containing a list of available ingredients.
* **Routing**: Passed directly to the primary agent orchestrator to invoke the web tool immediately.
* **Output**: A bulleted list of high-level meal concepts matched with active thread configuration IDs to retain context for subsequent questions.

### 2. Multi-Pass Multimodal Pipeline (Image Input)
* **Step 1: Visual Extraction**: Raw images are converted into base64 format inside an interactive file uploader context. This component is dispatched explicitly to the localized vision language model alongside strict context parameters prohibiting external internet callouts during pixel analysis.
* **Step 2: Structured Context Handoff**: The text response containing identified ingredients is parsed and injected dynamically into a follow-up compilation frame.
* **Step 3: Tool Execution**: The updated text sequence is pushed to the primary agent graph, prompting it to leverage web search queries to validate specific preparation styles, recipe titles, and ingredient pairings.

---

## Installation & Setup Guide

### Prerequisites
* **Python**: Version 3.13 or higher configured in a dedicated virtual workspace.
* **Package Runner**: `uv` or `pip` environment manager tools installed globally.
* **API Providers**: Active subscription access to OpenRouter (for OpenAI and NVIDIA endpoints) and Tavily AI search.

### 1. Configure Environment Variables
Create a `.env` file in the root directory of your workspace and populate your API credentials:
```ini
OPENROUTER_API_KEY=sk-or-v1-your-key-here
TAVILY_API_KEY=tvly-your-key-here

# Optional model configuration overrides
OPENROUTER_VISION_MODEL=nvidia/nemotron-nano-12b-v2-vl:free
OPENROUTER_CHEF_MODEL=openai/gpt-4o-mini
