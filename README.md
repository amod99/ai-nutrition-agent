# 🥗 Synthe-Health: Local Glucose Spike Analysis Agent

An end-to-end AI project demonstrating synthetic data generation, local LLM fine-tuning, and agentic deployment for personalized nutrition analysis.

## 🚀 Project Overview
This repository contains a full-stack AI implementation that transforms a general-purpose model into a specialized **Metabolic Nutritionist**. Unlike standard RAG systems, this agent uses a fine-tuned **Llama 3.2 3B** model to provide direct metabolic reasoning and glucose spike predictions without external database lookups.

### Key Technical Pillars
- **Synthetic Data Generation:** Created 500+ metabolic instruction pairs using Gemini 2.5 Flash and Pydantic for structural validation.
- **Efficient Fine-Tuning (QLoRA):** Leveraged **Unsloth** to train Llama 3.2 3B in 4-bit, reducing VRAM usage by 70% and making local training possible on consumer GPUs (RTX 30/40 series).
- **Local Deployment:** Model exported to GGUF and hosted via **Ollama** to serve as a high-speed, private inference engine for the nutritionist agent.

---

## 🛠️ Setup & Installation

### 1. Local Model Preparation (Ollama)
First, ensure [Ollama](https://ollama.com/) is installed. After running the fine-tuning notebook, register your model:
```bash
# Register the model using the provided Modelfile
ollama create nutrition-agent -f Modelfile

# Start the local server
ollama serve
