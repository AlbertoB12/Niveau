# Niveaus – Fine-Tuning eines LLM für CEFR-Sprachniveaus

LoRA-Fine-Tuning eines Mistral-Modells zur Umformulierung deutscher Texte zwischen den CEFR-Niveaus B1, B2 und C1. Das LLM wird auf einem synthetischen Datensatz trainiert, der mithilfe von Gemini erstellt wurde, um textspezifische Varianten für die einzelnen Niveaus zu generieren.

[Deutsch](README.de.md) | [English](README.md)

Um die Qualität von KI-generierten Bildungsinhalten zu verbessern, ist ein tiefes Verständnis sprachlicher Komplexität entscheidend. Dieses Projekt konzentriert sich darauf, ein bestehendes LLM so zu trainieren, dass es Texte zwischen den CEFR-Niveaus B1, B2 und C1 umformulieren kann.

---

## Prozess & Methodik

### Datensatz-Erstellung – Generierung synthetischer Daten:

- Zwei Open-Source-Datensätze (merlin_de(https://huggingface.co/datasets/UniversalCEFR/merlin_de) und elg_cefr_de) mit klassifizierten deutschen Texten dienten als Grundlage.  
- Ich habe diese Daten vorverarbeitet und anschließend Gemini genutzt, um einen synthetischen Datensatz zu erstellen. Für jeden B1-, B2- und C1-Text ließ ich das Modell zwei neue Versionen auf den jeweils anderen Niveaus generieren. So entstand ein umfassender „Instruction-Input-Output“-Datensatz, der sich ideal für Fine-Tuning eignet.

### Modellauswahl und Training:

- Ich wählte Mistral-7B-Instruct-v0.3, ein in Europa entwickeltes Modell, für diese Aufgabe.  
- 4-Bit-Quantisierung wurde eingesetzt, um das Training auf verfügbarer Hardware (NVIDIA H100 GPU auf Google Colab) zu ermöglichen.  
- Die LoRA-Methode (Low-Rank Adaptation) wurde für eine effiziente Anpassung genutzt. Statt das gesamte Modell neu zu trainieren, wurden nur kleine Adapter trainiert, was den Prozess erheblich beschleunigte.  
- Das Training erfolgte mit der TRL-Bibliothek von Hugging Face.  

---

## Eingesetzte Technologien & Fähigkeiten

**Frameworks & Bibliotheken:** Python, LangChain, Hugging Face (Transformers, Datasets, TRL, PEFT), Google Vertex AI, PyTorch, FastAPI, Streamlit, Pandas, Uvicorn, MatPlotLib, Seaborn, Torch, Gradio.  

**LLMs:** Google Gemini, Mistral 7B.  

**Techniken:** Prompt Engineering, Fine-Tuning (LoRA), 4-Bit-Quantisierung, Generierung synthetischer Daten, Datenaufbereitung, Analyse & Augmentation.  

**Deployment:** Google Colab, Ngrok, Streamlit, FastAPI, Hugging Face Spaces, GitHub.  
