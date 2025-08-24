# Niveau – Fine-Tuning an LLM for CEFR Language Levels
LoRA fine-tuning of a Mistral model to rephrase German texts between B1, B2, and C1 CEFR levels. The LLM is trained on a synthetic dataset, which was generated using Gemini to create level-specific text variations.

[Deutsch](README.de.md) | [English](README.md)

Huggingface: [https://huggingface.co/AlbertoB12/Mistral-7B-Instruct-german-level-tuner](https://huggingface.co/AlbertoB12/Mistral-7B-Instruct-german-level-tuner)

To improve the quality of AI-generated educational content, a deep understanding of linguistic complexity is crucial. This project focuses on training an existing LLM to rephrase texts between the CEFR levels B1, B2, and C1.

---

## Process & Methodology

### Dataset Creation – Synthetic Data Generation:

- Two open-source datasets (merlin_de and elg_cefr_de) with classified German texts served as the foundation.
- I preprocessed this data and then used Gemini to create a synthetic dataset. For each B1, B2, and C1 text, I had the model generate two new versions at the other levels, resulting in a comprehensive "Instruction-Input-Output" dataset ideal for fine-tuning.

### Model Selection and Training:

- I chose Mistral-7B-Instruct-v0.3, a model developed in Europe, for this task.
- 4-bit quantization was used to enable training on available hardware (NVIDIA H100 GPU on Google Colab).
- The LoRA (Low-Rank Adaptation) method was employed for efficient adaptation. Instead of retraining the entire model, only small adapters were trained, significantly speeding up the process.
- Training was conducted using the TRL library from Hugging Face.

---

## Applied Technologies & Skills

**Frameworks & Libraries:** Python, LangChain, Hugging Face (Transformers, Datasets, TRL, PEFT), Google Vertex AI, PyTorch, FastAPI, Streamlit, Pandas, Uvicorn, MatPlotLib, Seaborn, Torch, Gradio.

**LLMs:** Google Gemini, Mistral 7B.

**Techniques:** Prompt Engineering, Fine-Tuning (LoRA), 4-bit Quantization, Synthetic Data Generation, Data Preparation, Analysis & Augmentation.

**Deployment:** Google Colab, Ngrok, Streamlit, FastAPI, Hugging Face Spaces, GitHub.

---

## Generation Example

**Input text (C1):**
Der Krieg stellt stets eine tiefgreifende Zäsur für Gesellschaften dar, da er nicht nur Menschenleben kostet, sondern auch das Vertrauen in politische und soziale Strukturen erschüttert. Historiker betonen immer wieder, dass Konflikte selten aus einem einzigen Grund entstehen, sondern meist das Ergebnis komplexer ökonomischer, ideologischer und machtpolitischer Interessen sind. Besonders verheerend wirken sich moderne Kriege auf die Zivilbevölkerung aus, die durch Vertreibung, Hunger und Traumata nachhaltig gezeichnet wird. Trotz internationaler Abkommen und Institutionen gelingt es nur selten, bewaffnete Auseinandersetzungen rechtzeitig zu verhindern oder dauerhaft zu beenden. Umso dringlicher stellt sich die Frage, wie globale Zusammenarbeit gestärkt werden kann, um künftige Generationen vor ähnlichen Katastrophen zu bewahren.

**Model output (B1):**
Kriege sind immer eine tiefe Veränderung für Gesellschaften, denn sie kosten Menschenleben und beschädigen das Vertrauen in politische und soziale Strukturen. Historiker betonen immer wieder, dass Konflikte selten aus einem einzigen Grund entstehen, sondern meist das Ergebnis komplexer ökonomischer, ideologischer und machtpolitischer Interessen sind. Besonders schlimm sind moderne Kriege für die Zivilbevölkerung, die durch Vertreibung, Hunger und Traumata nachhaltig beeinflusst wird. Trotz internationaler Abkommen und Institutionen ist es nur selten möglich, bewaffnete Auseinandersetzungen rechtzeitig zu verhindern oder dauerhaft zu beenden. Es ist daher dringend notwendig, die globale Zusammenarbeit zu stärken, um künftigen Generationen vor ähnlichen Katastrophen zu schützen.
