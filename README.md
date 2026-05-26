# Multimodal Personal Chef with LangChain + OpenRouter NVIDIA Nemotron

![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge\&logo=python\&logoColor=white)
![LangChain](https://img.shields.io/badge/LangChain-121212?style=for-the-badge)
![OpenAI](https://img.shields.io/badge/OpenAI-412991?style=for-the-badge\&logo=openai\&logoColor=white)
![NVIDIA](https://img.shields.io/badge/NVIDIA-76B900?style=for-the-badge\&logo=nvidia\&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-F37626?style=for-the-badge\&logo=jupyter\&logoColor=white)
![Multimodal](https://img.shields.io/badge/Multimodal-AI-black?style=for-the-badge)
![Tavily](https://img.shields.io/badge/Tavily-AI_Search-blue?style=for-the-badge)

## Overview

This project demonstrates a multimodal AI personal chef assistant capable of processing:

* Text inputs
* Image uploads
* Conversational context
* Tool-based workflows
* Tavily-powered web search

The system combines LangChain agents with the OpenRouter hosted NVIDIA Nemotron Free model to create an interactive cooking assistant capable of recipe suggestions, ingredient analysis, food understanding, and contextual follow-up interactions.

---

## Features

* Multimodal text and image support
* Short-term conversational memory
* Tool calling and external function integration
* Tavily-powered AI web search and retrieval
* Base64 media encoding workflow
* OpenRouter NVIDIA Nemotron model integration
* LangChain agent orchestration
* Image understanding
* Context-aware responses

---

## Architecture

```text
User Input
   ├── Text
   └── Image
          │
          ▼
   LangChain Agent
          │
          ├── Short-Term Memory
          ├── Tool Calling
          ├── Tavily Search Integration
          └── OpenRouter NVIDIA Nemotron Free Model
                    │
                    ▼
            AI Chef Response
```

---

## Installation

Install the required dependencies:

```bash
pip install langchain openai python-dotenv ipywidgets sounddevice scipy tqdm
```

---

## Environment Variables

Create a `.env` file:

```env
OPENROUTER_API_KEY=your_api_key_here
TAVILY_API_KEY=your_api_key_here
```

---

## Core Components

### LangChain Agent

The application uses a LangChain agent configured with the OpenRouter NVIDIA Nemotron Free model to coordinate:

* Message handling
* Context management
* Tool execution
* Multimodal reasoning

---

### Short-Term Memory

The assistant maintains recent conversational context to support:

* Follow-up prompts
* Preference tracking
* Multi-step interactions
* Context-aware responses

---

### Tool Calling

The project supports external tool integration for:

* Nutritional analysis
* Recipe lookup
* Measurement conversion
* Grocery workflows
* Structured function execution
* Tavily web search integration

---

### Image Processing

Uploaded food images are processed and transmitted to the model using Base64 encoding.

Supported workflows include:

* Ingredient recognition
* Meal analysis
* Food identification
* Recipe recommendations

---

## Base64 Encoding Workflow

Media files are encoded into Base64 strings before being transmitted through API requests.

### Image Encoding

```text
Image File → Binary Data → Base64 String → API Request
```

---

## Multimodal Workflow

```text
1. User submits text or image
2. Media content is encoded when required
3. LangChain agent processes the request
4. Tools are invoked if necessary
5. OpenRouter NVIDIA Nemotron Free generates a response
6. Context is stored in short-term memory
```

---

## Tavily Integration

Tavily is integrated as a search and retrieval tool for obtaining real-time cooking, ingredient, and recipe information.

The agent can use Tavily-powered search workflows for:

* Recipe discovery
* Ingredient research
* Cooking recommendations
* External knowledge retrieval
* Real-time information access

---

## Tech Stack

| Technology       | Purpose                         |
| ---------------- | ------------------------------- |
| Python           | Core application development    |
| LangChain        | Agent orchestration             |
| OpenRouter API   | NVIDIA Nemotron model access    |
| Jupyter Notebook | Interactive experimentation     |
| ipywidgets       | File uploads                    |
| Tavily           | AI-powered search and retrieval |
| dotenv           | Environment management          |

---

## Future Improvements

* Persistent long-term memory
* Real-time voice conversations
* Webcam integration
* Meal planning workflows
* Grocery list automation
* Nutrition dashboards
* Recipe recommendation engine
* Mobile application support

---

## Result

This project provides a foundation for building production-ready multimodal AI assistants powered by the OpenRouter NVIDIA Nemotron Free model and capable of:

* Image understanding
* Tool usage
* Contextual conversations
* Intelligent workflow orchestration
