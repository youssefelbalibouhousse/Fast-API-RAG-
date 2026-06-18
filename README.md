<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Build a RAG API with FastAPI

**Project Link:** [View Project](http://learn.nextwork.org/projects/ai-devops-api)

**Author:** Youssef El bali  
**Email:** youssef.elbali@gmail.com

---

---

## Introducing Today's Project!

In this project, I'm going to create a local REST API that implements the full Retrieval-Augmented Generation pipeline This will help me get a competence that i will use in a project

### Key tools and concepts

### Challenges and wins

---

## Performing RAG Manually

In this step, I'm going to perform a manual RAG .
RAG stands for Retrieval-Augmented Generation.
First of all i need to setup my env and install all the dependencies. Finally pull the embedding model from Nomic AI.

Lets try to perform a retrieval manually 


![Image](http://learn.nextwork.org/lighthearted_olive_joyful_wolf/uploads/ai-devops-api_v3j7x5b9)

### Understanding the three parts of RAG

I performed RAG manually by add some information in a prompt so that the model can retrieve information for the next answer. 

### Comparing the two AI models

The key difference between nomic-embed-text and qwen is the purpose.
Nomic have the only task to embedd (convert) the different text to vectors. Nomic didn't chat or answer to question.
At the opposite you have qwen who respond by using the vector database who was filled by the vectors produced by Nomic

---

## Building a Personal Knowledge Base

In this step, I'm going to create a profil document then convert it to vectors by using the nomic-embed-text, after that i'm going to store all these vectors to ChromaDB and use qwen to retrieve data frome the data store ( ChromaDB).

![Image](http://learn.nextwork.org/lighthearted_olive_joyful_wolf/uploads/ai-devops-api_g3h7m2r5)

### Creating the profile document

I included information about my goals and some hobbies

### How semantic search finds relevant chunks

When I ask a question, ChromaDB got all the vectors stored and compute the distance between my query and the vectors by using Euclidian distance algortihme or Cosine distance for the semantic approch.

---

## Creating the RAG API with FastAPI

In this step, I'm going to build an API that accepts a question and returns an AI-generated answer. I'll test it using FastAPI

![Image](http://learn.nextwork.org/lighthearted_olive_joyful_wolf/uploads/ai-devops-api_j5m1r8t2)

### How the /ask endpoint works

When a question comes in, my endpoint take the query from the URL and search in ChromaDB the closest chunks from the vectore store and then add (augment) this context to the prompt. Finally with the help of the llm model, we can generate a answer that include the retrieve data and avoid hallucinations.
At last we obtain the right anwer about my profile.

### Testing with Swagger UI

I tested my API by asking who am I, and the AI answered with the name that i used in the profile doc, he also add my goal carrer without asking so i have to check on this parameter.

---

## Extending to a Multi-User AI Directory

In this project extension, I'm adding multi-user support because in a professional world you need a multiple acces for mutliple document and make sure thats available. Not only for profile but also for some kind of document where AI can be useful. 

Multi-tenancy is also important and means that all the users can have an isolated chat or exhange with the "client" without risk of data leaking for the benefit of another user.

![Image](http://learn.nextwork.org/lighthearted_olive_joyful_wolf/uploads/ai-devops-api_d5g9k3n7)

### Adding the POST /documents endpoint

In this project extension, I added a POST endpoint that allow users to add some data in form of a JSON

### Verifying multi-user filtering

---

## Wrapping Up

---

---
