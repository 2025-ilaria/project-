---
layout: default
title: Methodology
---

# <strong>Methodology<strong>

---
In this section, we present the methodology employed in the study of the Teatro Massimo di Palermo, including a **step-by-step description of the process** as well as an **explanations of the tools used**.


## Step-by-step process: 
🌐 **Initial Online Research**: we searched online for the most famous and important theaters in Italy, and one of them was the Teatro Massimo di Palermo.

🔍 **Exploration on ArCo**: we executed a SPARQL query on the [ArCo SPARQL endpoint](https://dati.cultura.gov.it/sparql), in order to verify the presence of Teatro Massimo on <a href="https://dati.beniculturali.it/arco/index.php">ArCo</a>. Even though it was present, we noticed that there was very little information available.

📊 **Comparison and Gap Identification**: we explored other theaters on ArCo for comparison and saw that, for example, the Teatro Comunale di Bologna had much more information, allowing us to identify the possible gaps.

🕵️ **Gap Confirmation**: we verified the validity of these possible gaps by running SPARQL queries that allowed us to confirm that this information was not present in ArCo. confirming the absence of certain cultural, architectural, and historical details.

💡 **LLM-Assisted Knowledge Retrieval**: we designed targeted prompts (zero-shot, few-shot, and chain-of-thought inspired) to gather missing information from <a href="https://chatgpt.com/">ChatGPT</a> and <a href="https://gemini.google.com/app">Gemini</a>.

⚖️ **Cross-Model Comparison**: we compared and validated the outputs from both LLMs to ensure reliability and completeness of the new cultural data.

📚 **RDF Triple Generation & Knowledge Graph Enrichment**: we converted new information into RDF triples aligned with the ArCo ontology and proposed <a href="https://en.wikipedia.org/wiki/Turtle_(syntax)">Turtle</a>-structured triples to extend the knowledge graph.

🖥️ **Website and Presentation Development**: we built a [GitHub-based website](https://github.com/2025-ilaria/project-)
and project presentation to document the methodology, results, and the role of LLMs in enriching a cultural heritage knowledge graph.

---

📌  _Let's take a closer look at the specific tools we used throughout the project_: ⬇️


## 1️⃣ ArCo and ArCo SPARQL endpoint: what are they?

The **ArCo Knowledge Graph** is a structured and semantically enriched representation of the Italian cultural heritage, developed by the <a href="https://it.wikipedia.org/wiki/Istituto_centrale_per_il_catalogo_e_la_documentazione">Italian Institute of Cultural Heritage (ICCD)</a> and the <a href="https://en.wikipedia.org/wiki/Ministry_of_Culture_(Italy)">Italian Ministry of Culture</a>.
It is built using <a href="https://en.wikipedia.org/wiki/Linked_data">Linked Open Data (LOD)</a> principles and the <a href="https://en.wikipedia.org/wiki/Resource_Description_Framework">Resource Description Framework (RDF)</a>, and it is based on a set of domain-specific ontologies (<a href="http://wit.istc.cnr.it/arco/lode/extract?lang=en&url=https://raw.githubusercontent.com/ICCD-MiBACT/ArCo/master/ArCo-release/ontologie/arco/arco.owl">the ArCo Ontologies</a>) that formally describe cultural heritage entities, such as artworks, monuments, archaeological sites, museums, archives, and their relationships.

The main goal of ArCo is to transform the vast catalog of Italian cultural heritage into a machine-readable, interoperable, and reusable knowledge graph. 

---

**ArCo SPARQL** refers to the SPARQL endpoint of the ArCo knowledge graph. It is the official query service that allows users to interrogate and retrieve data from ArCo using the SPARQL query language.

Through the ArCo SPARQL endpoint, researchers, developers, and practitioners can:

-Write queries to extract structured information (e.g., cultural sites, artworks, architects, restoration interventions).

-Explore relationships among cultural heritage entities defined in the ArCo ontology.

-Identify data gaps and enrichments needed for cultural heritage representation.

## 2️⃣ And RDF Triples: what are they?

**RDF triples** are the fundamental building blocks of the Resource Description Framework (RDF), a standard model for representing structured data on the <a href= "https://en.wikipedia.org/wiki/Semantic_Web">Semantic Web</a>. Each triple expresses a single fact or statement about a resource and is composed of three parts:

-**Subject** – the resource being described, usually represented as a <a href="https://it.wikipedia.org/wiki/Internationalized_Resource_Identifier">IRI</a>.

-**Predicate** – the property or type of relationship connecting the subject to the object (in our case case from the ArCo ontology)

-**Object** – the value or target of the property. It can be another IRI (another resource) or a literal value (string, number, date).

Purpose of creation: By encoding information as triples, data becomes structured, linkable, and queryable, forming a knowledge graph that machines can reason over and humans can explore.


## 3️⃣ What about LLMs (Large Language Models)?

LLMs, or **Large Language Models**, are a type of <a href="https://en.wikipedia.org/wiki/Artificial_intelligence">artificial intelligence (AI)</a> that are trained on enormous <a href="https://en.wikipedia.org/wiki/Data_set">datasets</a> of text and code to understand, generate, and process human-like language. These deep learning models, often based on the transformer architecture, can perform tasks like translation, summarization, question answering, content creation, and code generation, making them powerful tools for various natural language processing applications. 

---

We used **CHATGPT** and **GEMINI** ⬇️

ChatGPT is an AI-powered conversational model created by OpenAI, built on the <a href="https://en.wikipedia.org/wiki/Generative_pre-trained_transformer">GPT (Generative Pretrained Transformer)</a> architecture. It’s designed to interpret and produce human-like text. Trained on a wide range of textual data, it can engage in dialogue, create content, and support a variety of tasks.

Gemini is a collection of AI models developed by <a href="https://en.wikipedia.org/wiki/Google_DeepMind">Google DeepMind</a>, aimed at combining the strengths of large language models with advanced reasoning and problem-solving skills. It leverages <a href="https://en.wikipedia.org/wiki/State_of_the_art">state-of-the-art</a> techniques to improve the model’s capacity to generate nuanced, context-aware responses across a wide range of topics.

## 4️⃣ And finally, what is GitHub?
**GitHub** is an online platform that allows developers to store, manage, and collaborate on code projects using a system called <a href="https://en.wikipedia.org/wiki/Git">Git</a>, which tracks changes to files over time. It functions as both a <a href="https://en.wikipedia.org/wiki/Repository">repository</a> and a social workspace, letting programmers work together on the same project without overwriting each other’s work. Every change is recorded, so previous versions can be reviewed or restored, making it easier to manage complex projects.





[⬅️ Torna alla home]({{ '/' | relative_url }})

