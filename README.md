# workshop-llm
Workshop to create a RAG application using LLM models. 

This workshop is developed in Python 🐍 (Jupyter Notebook) and InterSystems IRIS.

The main purpose is to show you the main steps to create a RAG application using an LLM and a vector database.

You can find more in-depth information in https://learning.intersystems.com.

# What do you need to install? 
* [Git](https://git-scm.com/downloads) 
* [Docker](https://www.docker.com/products/docker-desktop) (if you are using Windows, make sure you set your Docker installation to use "Linux containers").
* [Docker Compose](https://docs.docker.com/compose/install/)
* [Visual Studio Code](https://code.visualstudio.com/download) + [InterSystems ObjectScript VSCode Extension](https://marketplace.visualstudio.com/items?itemName=daimor.vscode-objectscript)

# Setup
Build the image we will use during the workshop:

Clone the repository:
```bash
git clone https://github.com/intersystems-ib/workshop-llm
cd workshop-llm
```

Build the image:
```bash
docker compose build
```

Run the containers:
```bash
docker compose up -d
```

After running the containers, you should be able to access to:
* InterSystems IRIS [Management Portal](http://localhost:52774/csp/sys/UtilHome.csp). You can login using `superuser` / `SYS`
* [Jupyter Notebook](http://localhost:8888) 

# RAG Application

## Medicine Leaflet examples

You have some medicine leaflets (in spanish) in [./data](./data).

This example is about creating a RAG Q&A application that can answer questions about those medicine leaflets.

Open [Jupyter Notebook](http://localhost:8888), there you can find:
* [QA-PDF-LLM.ipynb](./jupyter/QA-PDF-LLM.ipynb) - RAG example using [MistralAI](https://mistral.ai) LLM 
* [QA-PDF-LLM.ipynb](./jupyter/QA-PDF-LLM.ipynb) - RAG example using a local LLM

![alt text](/images/jupyter.png)

You can test the project step by step or execute it at one time, feel free.

## Hoolefoods data model text to SQL

This example is about a company called Holefoods that sells food with some hole on it :)

Using the sales data model of the company, the goal is to create an assistant that can translate natural language questions into valid SQL that answer the question.

In [Jupyter Notebook](http://localhost:8888), you will find:
* [QA-SQL-LLM.ipynb](./jupyter/QA-SQL-LLM.ipynb) - text to SQL example using OpenAI LLM.