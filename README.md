# 🔧 Hackathon GenAI – Google Cloud & Vertex AI

Bienvenue dans ce dépôt GitHub contenant les notebooks utilisés lors du Hackathon dédié à l’exploration des capacités de la GenAI sur Google Cloud.

## 📚 Contenu du dépôt

Ce dépôt propose plusieurs notebooks pédagogiques pour vous aider à démarrer rapidement avec les outils d'IA générative sur Google Cloud, en particulier avec Vertex AI.

---

### 1. 🔐 Authentification locale via ADC avec impersonation

📄 `01_authentication_adc_impersonation.ipynb`

Ce notebook montre comment authentifier un environnement local avec un compte de service Google Cloud en utilisant les Application Default Credentials (ADC), combinées à l’option d’impersonation. Il permet ainsi de travailler de manière sécurisée, sans avoir à stocker de clés sensibles localement.

Fonctionnalités couvertes :
- Utilisation de gcloud auth application-default login
- Configuration de l’impersonation via les flags gcloud
- Vérification des credentials dans un notebook
- Exemple d'appel authentifié à Vertex AI

---

### 2. ✨ Prompt Engineering – Texte & Multimodal

📄 `02_prompt_engineering_text.ipynb`  
📄 `03_prompt_engineering_multimodal.ipynb`

Deux notebooks pour explorer les bonnes pratiques de conception de prompts pour les modèles de langage.

- Prompt engineering sur du texte (LLM) : structuration, formats, templates.
- Prompt engineering multimodal (texte + image) : création de prompts combinés, appels aux modèles multimodaux de Vertex AI.

---

### 3. 🧠 Exemple de Retrieval-Augmented Generation (RAG)

📄 `04_rag_vertex_ai_example.ipynb`

Ce notebook montre comment mettre en place un flux de type RAG simple, combinant :

- Création et chargement d’un index documentaire
- Utilisation d’un modèle LLM hébergé sur Vertex AI
- Récupération des documents les plus pertinents via recherche sémantique
- Génération de réponse contextualisée par le modèle

Idéal pour découvrir les bases de la génération augmentée par la recherche avec Vertex AI.

---

## 🔧 Prérequis

- Un projet Google Cloud avec Vertex AI et IAM activés
- Python 3.8+
- gcloud CLI installé et configuré
- Bibliothèques Python : vertexai, langchain, google-auth, pandas, etc. (voir requirements.txt si fourni)

---

## 🚀 Lancement rapide

1. Clonez le dépôt :
```bash
git clone https://github.com/votre-utilisateur/hackathon-genai.git
cd hackathon-genai
