# 🔍 Arabic News Entity Extractor

An AI-powered NLP tool designed to transform unstructured Arabic news articles into structured, machine-readable JSON data. This project leverages a fine-tuned **Qwen 2.5 (1.5B)** model with a specialized adapter to perform high-accuracy Information Extraction (IE) and Named Entity Recognition (NER).

[![Hugging Face Space](https://img.shields.io/badge/%F0%9F%A4%97%20Hugging%20Face-Spaces-blue)](https://huggingface.co/spaces/duclo90/Arabic_News_Entity_Extractor)
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/ducloser90/Arabic_News_Entity_Extractor/blob/main/Arabic_News_Entity_Extractor.ipynb)
[![Model: Qwen 2.5](https://img.shields.io/badge/Model-Qwen2.5--1.5B-purple)](https://huggingface.co/Qwen/Qwen2.5-1.5B-Instruct)
[![Adapter: structured_output](https://img.shields.io/badge/%F0%9F%A4%97%20HF%20Adapter-structured__output-orange)](https://huggingface.co/duclo90/structured_output)
[![License: Apache 2.0](https://img.shields.io/badge/License-Apache%202.0-yellow.svg)](LICENSE)

## 📖 Project Overview

Extracting structured data from Arabic text is often difficult due to linguistic complexity and morphological variations. This application automates the transition from raw prose to structured data. 

Here is a concrete example of how an Arabic sports article is processed into structured JSON:

![Project Workflow Example](https://github.com/user-attachments/assets/1b3f2389-851e-42f2-b652-629a87c1fc55)
![Image](https://github.com/user-attachments/assets/889bc774-6a34-4674-a5f3-623e3e702c94)



### Key Capabilities:
* **SEO Title Generation:** Extracts or generates optimized headlines.
* **Key Point Summarization:** Distills long articles into 1-5 core points.
* **Zero-Shot Categorization:** Classifies news into sectors (Politics, Economy, Tech, etc.).
* **Named Entity Recognition (NER):** Extracts people, locations, and organizations.
* **JSON Schema Enforcement:** Guarantees output follows a strict Pydantic structure.

---

## ⚡ Fast Inference (Google Colab)

While the Hugging Face Space is convenient, it typically runs on **CPU**, which can take 30-60 seconds to process a story. 

**For 10x faster performance**, use the provided Jupyter Notebook on Google Colab to leverage a free T4 GPU:

1. Click the **Open in Colab** badge at the top of this README.
2. In Colab, go to **Runtime > Change runtime type** and ensure **T4 GPU** is selected.
3. Run the cells to launch the Gradio interface directly in your browser.



---

## 🛠️ Technical Stack

* **Base Model:** `Qwen/Qwen2.5-1.5B-Instruct`
* **PEFT Adapter:** `duclo90/structured_output`
* **Interface:** [Gradio](https://gradio.app/)
* **Core Libraries:** `transformers`, `peft`, `pydantic`, `json_repair`

## 🚀 Local Installation

If you wish to run the project locally instead of using Colab or Hugging Face:

1. **Clone the Repository:**
    ```bash
    git clone [https://github.com/ducloser90/Arabic_News_Entity_Extractor.git](https://github.com/ducloser90/Arabic_News_Entity_Extractor.git)
    cd Arabic_News_Entity_Extractor
    ```

2. **Create a Virtual Environment:**
    ```bash
    python -m venv venv
    source venv/bin/activate  # On Windows: venv\Scripts\activate
    ```

3. **Install Dependencies:**
    ```bash
    pip install -r requirements.txt
    ```

4. **Run the App:**
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
