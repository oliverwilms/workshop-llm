# workshop-llm
Workshop to create a RAG application to use LLM models. This workshop is developed in Python using Jupyter Notebook connected using the official libraries to IRIS.

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

The main purpose of this example is to identify the main steps to create a RAG application using MISTRAL as LLM and IRIS as vector database to save and search the specific context.

## Create table for document & vector representation

First, you need to create the table where we will store document chunks and their vector embeddings.

Open IRIS [SQL Explorer](http://localhost:52774/csp/sys/exp/%25CSP.UI.Portal.SQL.Home.zen?$NAMESPACE=LLMRAG) in `LLMRAG` namespace:

```sql
CREATE TABLE LLMRAG.DOCUMENTCHUNK (
    Document VARCHAR(500),
    Phrase VARCHAR(1000), 
    VectorizedPhrase VECTOR(DECIMAL, 384)
)
```

We could also do that directly from Python or connecting from SQL tools like DBeaver.

# Testing with Jupyter Notebook

This project is devolped in Python using Jupyter Notebook, you can access to it from [Jupyter Notebook](http://localhost:8888), there you can find:
* [LLMTest.ipynb](./jupyter/LLMTest.ipynb) - RAG example using [MistralAI](https://mistral.ai) LLM 
* [LLMLocal.ipynb](./jupyter/LLMLocal.ipynb) - RAG example using a local LLM

![alt text](/images/jupyter.png)

You can test the project step by step or execute it at one time, feel free.