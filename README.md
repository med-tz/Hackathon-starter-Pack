## 🔧 Hackathon GenAI – Google Cloud & Vertex AI

Bienvenue dans ce dépôt GitHub contenant les notebooks utilisés lors du Hackathon dédié à l’exploration des capacités de la GenAI sur Google Cloud.

### 📚 Contenu du dépôt

Ce dépôt propose plusieurs notebooks pédagogiques pour vous aider à démarrer rapidement avec les outils d'IA générative sur Google Cloud, en particulier avec Vertex AI.

## 🔧 Setup & Prérequis

Avant de commencer avec les notebooks, assurez-vous d’avoir l’environnement correctement configuré.

### 🐍 Installation de Python

#### **Windows**
1. Si vous n’avez pas encore installé Python sur votre système Windows, téléchargez et installez le dernier installateur Python3 depuis la [page de téléchargement de Python](https://www.python.org/downloads/release/python-3100/).
   - Assurez-vous de cocher la case pendant l’installation pour **ajouter Python au PATH**. Elle est généralement libellée **Add Python 3.X to PATH**.

2. Une fois Python installé, vous devriez pouvoir ouvrir une fenêtre de commande, taper `python`, appuyer sur ENTRÉE et voir l’invite Python apparaître. Tapez `quit()` pour en sortir. Vous devriez également pouvoir exécuter la commande `pip` et voir les options affichées. Si ces deux commandes fonctionnent, alors tout est prêt.
   - Si vous ne pouvez pas exécuter `python` ou `pip` depuis l’invite de commande, vous devrez peut-être ajouter manuellement le chemin du dossier d’installation de Python à la variable d’environnement PATH de Windows.
     - Le moyen le plus simple de le faire est de trouver le raccourci Python dans le menu démarrer, faire un clic droit dessus et localiser le chemin du fichier `python.exe`.
     - Il s’agit probablement de quelque chose comme `C:\Users\<NOM_UTILISATEUR>\AppData\Local\Programs\Python\Python310`.
     - Ouvrez la fenêtre des **Paramètres système avancés**, allez dans l’onglet **Avancé**, puis cliquez sur le bouton **Variables d’environnement**.
     - Créez une nouvelle variable système :
       - Nom de la variable : `PYTHON_HOME`
       - Valeur de la variable : <chemin_d’installation_de_Python>
     - Modifiez ensuite la variable système `PATH` en ajoutant `;%PYTHON_HOME%\;%PYTHON_HOME%;%PYTHON_HOME%\Scripts\` à la fin de sa valeur.
     - Fermez toutes les fenêtres, ouvrez une invite de commande et assurez-vous que les commandes `python` et `pip` fonctionnent.


#### **macOS**
macOS est livré avec une version native de Python. Actuellement, il s’agit généralement de Python 2, qui est obsolète. Pour utiliser la plupart des applications Python modernes, vous devez installer Python 3. Python 2 et Python 3 peuvent coexister sur la même machine sans problème, ce qui est même nécessaire, car macOS utilise encore Python 2 pour certaines fonctionnalités système.

#### Option 1 : Installer la version officielle de Python
1. Rendez-vous sur la [page de téléchargement de Python](https://www.python.org/downloads/release/python-3100/).
2. Cliquez sur le bouton **Download Python 3.x.x**.
3. Suivez les étapes de l’assistant d’installation.
4. Une fois l’installation terminée, une fenêtre Finder s’ouvrira avec plusieurs fichiers `.command`.
   - Double-cliquez sur `Install Certificates.command` et `Update Shell Profile.command` pour exécuter chacun de ces fichiers.
   - Fermez les fenêtres une fois terminé.
5. Ouvrez l’application **Terminal** et exécutez `python3` pour accéder à l’interpréteur Python. Tapez `quit()` pour sortir. Vérifiez également que `pip` (le gestionnaire de paquets Python) est bien installé en exécutant `pip3 -V`.

#### Option 2 : Installer avec Homebrew
[Homebrew](https://brew.sh/) est un gestionnaire de paquets pour macOS, similaire à ceux des systèmes Linux. Suivez les étapes ci-dessous pour installer Homebrew et une version à jour de Python.

1. Ouvrez le **Terminal** et exécutez : `xcode-select --install`. Une fenêtre va s’ouvrir, cliquez sur **'Get Xcode'** pour l’installer via l’App Store.
2. Installez Homebrew avec la commande :  
   `/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"`
3. Installez la dernière version de Python 3 : `brew install python`
4. Une fois Python installé, ouvrez **Terminal**, tapez `python3`, appuyez sur ENTRÉE et vous verrez une invite Python 3.X.X. Tapez `quit()` pour quitter. Vérifiez aussi que la commande `pip3` fonctionne.


#### **Linux** 

- **Raspberry Pi OS** pourrait nécessiter Python et PIP :
  - Installez-les : `sudo apt install -y python3-pip`

- **Distributions Debian (Ubuntu)** peuvent aussi nécessiter Python et PIP :
  - Mettez à jour la liste des dépôts : `sudo apt update`
  - Installez Python et PIP : `sudo apt install -y python3-pip`

- **Distributions RHEL (CentOS)** nécessitent généralement PIP :
  - Installez le paquet EPEL : `sudo yum install -y epel-release`
  - Installez PIP : `sudo yum install -y python3-pip`
### ☁️ Installation du SDK Google Cloud

Le SDK Google Cloud est un ensemble d’outils en ligne de commande permettant de gérer vos ressources et services sur Google Cloud Platform.



1. Téléchargez l’installateur ici : [Google Cloud SDK](https://dl.google.com/dl/cloudsdk/channels/rapid/GoogleCloudSDKInstaller.exe?hl=fr)

2. Exécutez le fichier `.exe` téléchargé et suivez les instructions d'installation.

3. Une fois l'installation terminée, cochez les options suivantes :
   - **Start Google Cloud SDK Shell**
   - **Run 'gcloud init' to configure the Google Cloud CLI**

4. Une fenêtre de commande s’ouvrira automatiquement :
   - Choisissez **"Create a new configuration"** lorsqu'on vous le propose.
   - Entrez un nom pour la configuration.
   - Dans **"Sélectionner un compte"**, choisissez **"Sign in with a new Google Account"**.
   - Un onglet s’ouvrira dans votre navigateur où vous devrez vous connecter avec votre compte **L'Oréal**.
   - Dans **"Choisir un projet cloud à utiliser"**, sélectionnez **"Saisir un ID de projet"** et entrez l’ID suivant : `oa-bta-learning-dv`
   - Si un message indique que l'ID du projet n'existe pas, tapez `y` pour continuer.

5. Enfin, dans la ligne de commande, tapez la commande suivante :

```bash
gcloud auth application-default login --impersonate-service-account SERVICE_ACCT_EMAIL
```

Remplacez `SERVICE_ACCT_EMAIL` par l’adresse email du compte de service assigné à votre équipe.
##  Notebooks
### 1. ✨ Prompt Engineering – Texte & Multimodal

📄 `01_prompt_engineering_notebook.ipynb`  

Deux notebooks pour explorer les bonnes pratiques de conception de prompts pour les modèles de langage.

- Prompt engineering sur du texte (LLM) : structuration, formats, templates.
- Prompt engineering multimodal (texte + image) : création de prompts combinés, appels aux modèles multimodaux de Vertex AI.



### 2. 🧠 Exemple de Retrieval-Augmented Generation (RAG)

📄 `02_rag_vertex_ai_example.ipynb`

Ce notebook montre comment mettre en place un flux de type RAG simple, combinant :

- Création et chargement d’un index documentaire
- Utilisation d’un modèle LLM hébergé sur Vertex AI
- Récupération des documents les plus pertinents via recherche sémantique
- Génération de réponse contextualisée par le modèle

Idéal pour découvrir les bases de la génération augmentée par la recherche avec Vertex AI.




## 🚀 Lancement rapide

1. Clonez le dépôt :
```bash
git clone https://github.com/med-tz/Hackathon-starter-Pack.git
cd Hackathon-starter-Pack
