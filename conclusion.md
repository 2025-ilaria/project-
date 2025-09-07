---
layout: default
title: Conclusion
---

# <strong>Conclusion<strong>


---

Our project on the **Teatro Massimo di Palermo** showed how **semantic web technologies** and **Large Language Models (LLMs)** can work together to improve the way we document and understand cultural heritage. We noticed that the **ArCo knowledge graph** was missing important information about this famous opera house, so we followed a step-by-step approach to collect, check, and organize details about its history, architecture, and cultural significance.

---

## ⚠️ Challenges 


**🧠 CHOOSING OUR TOPIC**

One of the initial challenges we faced was identifying a **suitable topic** that was both **culturally significant** and **underrepresented** in the ArCo Knowledge Graph.
While many well-known cultural heritage sites were already documented with detailed information, finding a meaningful gap required careful exploration. Discovering that Teatro Massimo di Palermo, despite its status, lacked substantial structured data was both surprising and motivating. 

**📌 How we overcame it** ➡️ Doing meticulous research and running SPARQL queries on ArCo.

---
**🔍 SPARQL AND SEMANTIC EXPLORATION**

Exploring the ArCo knowledge graph and comparing it with other cultural institutions, such as the Teatro Comunale of Bologna, allowed us to identify specific gaps. SPARQL
proved to be a powerful but **complex tool**: although it was initially difficult to understand, we progressively learned how to write more accurate queries and use them to
verify the availability of data. A significant part of the challenge consisted in identifying the correct **ArCo properties** to use, selecting the appropriate vocabulary
often required careful analysis and a deep understanding of the ontology’s structure.

**📌 How we overcame it** ➡️ Analyzing existing SPARQL queries. 

---

**🧪 PROMPT ENGINEERING FOR LLMS**

It was not easy to find the right way to ask LLMs for structured data. We needed to experiment with **few-shot**, **zero-shot**, and **chain-of-thought** techniques.

**📌 How we overcame it** ➡️ Learning prompt patterns.

---
**🧩 RDF TRIPLES**

Generating **RDF triples** was also challenging: identifying the correct **predicates** and creating the right **prompts** required multiple iterations and a deep understanding of both the ontology and the models. 

**📌How we overcame it** ➡️ Asking LLMs and analyzing existing triples.

---

**🌐 WEBSITE DEVELOPMENT ON GITHUB**

Another major challenge was building our website using **GitHub**. As first-time users, we needed time to understand how the platform works—how to organize files and publish pages. Despite the initial difficulties, we successfully created a **well-structured site** to present our work.

**📌 How we overcame it** ➡️ Experimentation and tutorials.

---

## 📍Final considerations 

**🔸 SPARQL AND ONTOLOGICAL REASONING**

🔸 **SPARQL Queries **
By exploring the ArCo knowledge graph and comparing it with better-documented sites (like the Teatro Comunale of Bologna), we found clear **gaps** in the data. **SPARQL** turned out to be a key tool for checking these gaps, showing why it’s important to write **accurate queries** and understand how the **ontology** works when working with cultural heritage data. 


---
**🔸 LLMS AS KNOWLEDGE ALLIES**

LLMs like **ChatGPT** and **Gemini** offered a complementary approach to traditional semantic technologies. Through careful **prompt design**, we successfully extracted
**high-quality information** suitable for **RDF conversion**. While ChatGPT showed strong coherence in reasoning-based prompts, Gemini proved more effective when guided
with structured examples, underlining the importance of model-aware prompting strategies.

---
**🔸KNOWLEDGE INTEGRATION AND IMPACT**

The retrieved knowledge was transformed into **RDF triples** aligned with ArCo ontologies and formatted in **Turtle syntax**, ready to be integrated into the semantic web. 
This not only helps close existing data gaps but also paves the way for more inclusive and representative cultural heritage knowledge graphs.




[⬅️ Torna alla Home]({{ '/' | relative_url }})
