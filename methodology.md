---
layout: default
title: Methodology
---

# <strong>Methodology<strong>

---
In this section, we present the methodology employed in the study of the Teatro Massimo di Palermo, including a **step-by-step description of the process** as well as an **explanations of the tools used**.


## Step-by-step process: 
🌐 **Initial Online Research**: we searched online for the most famous and important theaters in Italy, and one of them was the Teatro Massimo di Palermo.

🔍 **Exploration on ArCo**: we asked LLMs (<a href="https://chatgpt.com/">ChatGPT</a> and <a href="https://gemini.google.com/app">Gemini</a>) to generate SPARQL queries targeting the [ArCo SPARQL endpoint](https://dati.cultura.gov.it/sparql)
, in order to verify the presence of Teatro Massimo on <a href="https://dati.beniculturali.it/arco/index.php">ArCo</a>. Even though it was present, we noticed that there was very little information available.

📊 **Comparison and Gap Identification**: we explored other theaters on ArCo for comparison and saw that, for example, the Teatro Comunale in Bologna had much more information, allowing us to identify the possible gaps.

🕵️ **Gap Confirmation**: we verified the validity of these possible gaps by running SPARQL queries that allowed us to confirm that this information was not present in ArCo. confirming the absence of certain cultural, architectural, and historical details.

💡 **LLM-Assisted Knowledge Retrieval**: we designed targeted prompts (zero-shot, few-shot, and chain-of-thought inspired) to gather missing information from Chat GPT and Gemini.

⚖️ **Cross-Model Comparison**: we compared and validated the outputs from both LLMs to ensure reliability and completeness of the new cultural data.

📚 **RDF Triple Generation & Knowledge Graph Enrichment**: we converted new information into RDF triples aligned with the ArCo ontology and proposed Turtle-structured triples to extend the knowledge graph.

🖥️ **Website and Presentation Development**: we built a [GitHub-based website](https://github.com/2025-ilaria/project-)
and project presentation to document the methodology, results, and the role of LLMs in enriching a cultural heritage knowledge graph.

---

📌  _Let's take a closer look at the specific tools we used throughout the project_  📌 :


## 1️⃣ ArCo and ArCo SPARQL endpoint: what are they?

The **ArCo Knowledge Graph** is a structured and semantically enriched representation of the Italian cultural heritage, developed by the Italian Institute of Cultural Heritage (ICCD) and the Italian Ministry of Culture.
It is built using Linked Open Data (LOD) principles and the Resource Description Framework (RDF), and it is based on a set of domain-specific ontologies (the ArCo Ontologies) that formally describe cultural heritage entities, such as artworks, monuments, archaeological sites, museums, archives, and their relationships.

The main goal of ArCo is to transform the vast catalog of Italian cultural heritage into a machine-readable, interoperable, and reusable knowledge graph. 

---

**ArCo SPARQL** refers to the SPARQL endpoint of the ArCo knowledge graph. It is the official query service that allows users to interrogate and retrieve data from ArCo using the SPARQL query language (the W3C standard for querying RDF data).

Through the ArCo SPARQL endpoint, researchers, developers, and practitioners can:

-Write queries to extract structured information (e.g., cultural sites, artworks, architects, restoration interventions).

-Explore relationships among cultural heritage entities defined in the ArCo ontology.

-Identify data gaps and enrichments needed for cultural heritage representation.

## 2️⃣ And RDF Triples: what are they?

**RDF triples** are the fundamental building blocks of the Resource Description Framework (RDF), a standard model for representing structured data on the Semantic Web. Each triple expresses a single fact or statement about a resource and is composed of three parts:

-**Subject** – the resource being described, usually represented as a URI.

-**Predicate** – the property or type of relationship connecting the subject to the object (in our case case from the ArCo ontology)

-**Object** – the value or target of the property. It can be another URI (another resource) or a literal value (string, number, date).

Purpose of creation: By encoding information as triples, data becomes structured, linkable, and queryable, forming a knowledge graph that machines can reason over and humans can explore.


## 3️⃣ What about LLMs (Large Language Models)?

LLMs, or **Large Language Models**, are a type of artificial intelligence (AI) that are trained on enormous datasets of text and code to understand, generate, and process human-like language. These deep learning models, often based on the transformer architecture, can perform tasks like translation, summarization, question answering, content creation, and code generation, making them powerful tools for various natural language processing applications. 

---

We used **CHATGPT** and **GEMINI** ⬇️

ChatGPT is an AI-powered conversational model created by OpenAI, built on the GPT (Generative Pretrained Transformer) architecture. It’s designed to interpret and produce human-like text. Trained on a wide range of textual data, it can engage in dialogue, create content, and support a variety of tasks.

Gemini is a collection of AI models developed by Google DeepMind, aimed at combining the strengths of large language models with advanced reasoning and problem-solving skills. It leverages state-of-the-art techniques to improve the model’s capacity to generate nuanced, context-aware responses across a wide range of topics.

## 4️⃣ And finally, what is GitHub?
**GitHub** is an online platform that allows developers to store, manage, and collaborate on code projects using a system called Git, which tracks changes to files over time. It functions as both a repository and a social workspace, letting programmers work together on the same project without overwriting each other’s work. Every change is recorded, so previous versions can be reviewed or restored, making it easier to manage complex projects. GitHub also enables collaboration through features like branching, pull requests, and issue tracking, which allow multiple contributors to propose changes, discuss improvements, and merge updates safely.





[⬅️ Torna alla home]({{ '/' | relative_url }})

