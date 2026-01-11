# 🔍 Arabic News Entity Extractor

An AI-powered NLP tool designed to transform unstructured Arabic news articles into structured, machine-readable JSON data. This project leverages a fine-tuned **Qwen 2.5 (1.5B)** model with a specialized adapter to perform high-accuracy Information Extraction (IE) and Named Entity Recognition (NER).

[![Hugging Face Space](https://img.shields.io/badge/%F0%9F%A4%97%20Hugging%20Face-Spaces-blue)](https://huggingface.co/spaces/YOUR_USERNAME/YOUR_SPACE_NAME)
[![Model: Qwen 2.5](https://img.shields.io/badge/Model-Qwen2.5--1.5B-purple)](https://huggingface.co/Qwen/Qwen2.5-1.5B-Instruct)
[![License: Apache 2.0](https://img.shields.io/badge/License-Apache%202.0-yellow.svg)](LICENSE)

## 📖 Project Overview

Extracting structured data from Arabic text is often difficult due to linguistic complexity and morphological variations. This application automates the transition from raw prose to structured data. 



### Key Capabilities:
* **SEO Title Generation:** Extracts or generates optimized headlines.
* **Key Point Summarization:** distills long articles into 1-5 core points.
* **Zero-Shot Categorization:** Classifies news into sectors (Politics, Economy, Tech, etc.).
* **Named Entity Recognition (NER):** Extracts people, locations, and organizations.
* **JSON Schema Enforcement:** Guarantees output follows a strict Pydantic structure.

## 🛠️ Technical Stack

* **Base Model:** `Qwen/Qwen2.5-1.5B-Instruct`
* **PEFT Adapter:** `duclo90/structured_output`
* **Interface:** [Gradio](https://gradio.app/)
* **Core Libraries:** `transformers`, `peft`, `pydantic`, `json_repair`

## 🚀 Local Installation

If you wish to run the project locally instead of on Hugging Face Spaces:

1.  **Clone the Repository:**
    ```bash
    git clone [https://github.com/your-username/arabic-news-extractor.git](https://github.com/your-username/arabic-news-extractor.git)
    cd arabic-news-extractor
    ```

2.  **Create a Virtual Environment:**
    ```bash
    python -m venv venv
    source venv/bin/activate  # On Windows: venv\Scripts\activate
    ```

3.  **Install Dependencies:**
    ```bash
    pip install -r requirements.txt
    ```

4.  **Run the App:**
    ```bash
    python app.py
    ```

## 📊 Extraction Schema

The model is constrained to output data according to this strict JSON format:

```json
{
  "story_title": "Optimized Title Here",
  "story_keywords": ["keyword1", "keyword2"],
  "story_summary": [
    "Key point 1",
    "Key point 2"
  ],
  "story_category": "Economy",
  "story_entities": [
    {
      "entity_value": "Name/Place",
      "entity_type": "person-male/location"
    }
  ]
}
