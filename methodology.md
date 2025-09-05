---
layout: default
title: Methodology
---

# <strong>Methodology<strong>


This project focuses on the Teatro Massimo Vittorio Emanuele in Palermo, with the main goal of enriching the cultural heritage data available in the ArCo knowledge graph. The methodology combines the structured information already provided by ArCo with the generative capabilities of Large Language Models (LLMs), such as ChatGPT and Gemini.

The step-by-step process includes: 

🎯 **Topic Selection**: Defined the focus of the project on Teatro Massimo Vittorio Emanuele in Palermo, with the aim of enriching the ArCo knowledge graph by combining cultural heritage data with LLM-generated knowledge.

🔎 **Exploration of ArCo**: Carried out a systematic exploration of the ArCo knowledge graph [ArCo](http://wit.istc.cnr.it/arco)
 to identify what information was already available about Teatro Massimo, and to gain an initial understanding of its data coverage.

📊 **Gap Analysis**: Identified missing data by comparing the ArCo page of Teatro Massimo with that of the Teatro Comunale of Bologna, which provided a more complete knowledge structure.

🤖 **SPARQL Query Generation with LLMs**: Asked ChatGPT and Gemini to generate SPARQL queries targeting the [ArCo SPARQL endpoint](https://dati.cultura.gov.it/sparql)
, in order to verify which specific information was already stored in the knowledge graph.

🕵️ **Gap Confirmation**: Validated the gaps by running the generated SPARQL queries and confirming the absence of certain cultural, architectural, and historical details.

💡 **LLM-Assisted Knowledge Retrieval**: Designed targeted prompts (zero-shot, few-shot, and chain-of-thought inspired) to gather missing information from [ChatGPT](https://chatgpt.com/)
 and [Gemini](https://gemini.google.com/app)


⚖️ **Cross-Model Comparison**: Compared and validated the outputs from both LLMs to ensure reliability and completeness of the new cultural data.

📚 **RDF Triple Generation**: Translated the newly acquired information into RDF triples, strictly aligned with the ArCo ontology.

🌐 **Knowledge Graph Enrichment**: Proposed structured triples in Turtle syntax to extend the ArCo knowledge graph, ensuring semantic coherence and adherence to cultural heritage standards.

🖥️ **Website and Presentation Development**: Built a GitHub-based website [GitHub-based website](https://github.com/2025-ilaria/project-)
and project presentation to document the methodology, results, and the role of LLMs in enriching a cultural heritage knowledge graph.


Let's take a closer look at the specific tools we used throughout the project: 

# <strong>ArCo and ArCo SPARQL endpoint: WHAT ARE THEY?<strong>

The **ArCo Knowledge Graph** is a structured and semantically enriched representation of the Italian cultural heritage, developed by the Italian Institute of Cultural Heritage (ICCD) and the Italian Ministry of Culture.
It is built using Linked Open Data (LOD) principles and the Resource Description Framework (RDF), and it is based on a set of domain-specific ontologies (the ArCo Ontologies) that formally describe cultural heritage entities, such as artworks, monuments, archaeological sites, museums, archives, and their relationships.

The main goal of ArCo is to transform the vast catalog of Italian cultural heritage into a machine-readable, interoperable, and reusable knowledge graph. 

In short, the ArCo Knowledge Graph is the largest open knowledge graph on Italian cultural heritage, designed to make cultural data FAIR (Findable, Accessible, Interoperable, Reusable) and to support semantic enrichment, AI-based analysis, and innovative digital services.

---

**ArCo SPARQL** refers to the SPARQL endpoint of the ArCo knowledge graph. It is the official query service that allows users to interrogate and retrieve data from ArCo using the SPARQL query language (the W3C standard for querying RDF data).

Through the ArCo SPARQL endpoint, researchers, developers, and practitioners can:

-Write queries to extract structured information (e.g., cultural sites, artworks, architects, restoration interventions).

-Explore relationships among cultural heritage entities defined in the ArCo ontology.

-Identify data gaps and enrichments needed for cultural heritage representation.

In short, ArCo SPARQL is the interface that connects users to the ArCo knowledge graph, enabling semantic search and data analysis.



[⬅️ Torna alla home]({{ '/' | relative_url }})

