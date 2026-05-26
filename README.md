# Multimodal Personal Chef with LangChain

![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge\&logo=python\&logoColor=white)
![LangChain](https://img.shields.io/badge/LangChain-121212?style=for-the-badge)
![OpenAI](https://img.shields.io/badge/OpenAI-412991?style=for-the-badge\&logo=openai\&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-F37626?style=for-the-badge\&logo=jupyter\&logoColor=white)
![Multimodal](https://img.shields.io/badge/Multimodal-AI-black?style=for-the-badge)

## Overview

This project demonstrates a multimodal AI personal chef assistant capable of processing:

* Text inputs
* Image uploads
* Conversational context
* Tool-based workflows

The system combines OpenAI multimodal models with LangChain agents to create an interactive cooking assistant capable of recipe suggestions, ingredient analysis, food understanding, and contextual follow-up interactions.

---

## Features

* Multimodal text and image support
* Short-term conversational memory
* Tool calling and external function integration
* Base64 media encoding workflow
* OpenAI multimodal model integration
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
          └── OpenAI Multimodal Model
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
OPENAI_API_KEY=your_api_key_here
```

---

## Core Components

### LangChain Agent

The application uses a LangChain agent configured with OpenAI multimodal models to coordinate:

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
5. OpenAI multimodal model generates a response
6. Context is stored in short-term memory
```

---

## Tech Stack

| Technology       | Purpose                      |
| ---------------- | ---------------------------- |
| Python           | Core application development |
| LangChain        | Agent orchestration          |
| OpenAI API       | Multimodal reasoning         |
| Jupyter Notebook | Interactive experimentation  |
| ipywidgets       | File uploads                 |
| dotenv           | Environment management       |

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

This project provides a foundation for building production-ready multimodal AI assistants capable of:

* Image understanding
* Tool usage
* Contextual conversations
* Intelligent workflow orchestration
