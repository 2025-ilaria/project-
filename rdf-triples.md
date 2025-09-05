---
layout: default
title: RDF Triples
---

# RDF Triples


---

In this section there are all **RDF Triples** generated for each gap.  

1️⃣ **RDF Triple Full Name** 

🔍We asked CHAT GPT to create a triple using the **zero-shot prompt**

![Screenshot](assets/css/Screenshot%20Chat%20prompt%20name%20triple.png)

Here the result

```rdf
@prefix arco: <https://w3id.org/arco/ontology/arco/> .
@prefix cis: <http://dati.beniculturali.it/cis/> .
@prefix rdfs: <http://www.w3.org/2000/01/rdf-schema#> .

<http://dati.beniculturali.it/iccd/schede/resource/CulturalInstituteOrSite/S012166_Teatro_Massimo>
    a arco:CulturalInstituteOrSite ;
    cis:institutionalCISName "Teatro Massimo Vittorio Emanuele"@it .
```
---
We asked Chat to create it using the following information: 

> **Subject**:Teatro Massimo di Palermo, IRI <http://dati.beniculturali.it/iccd/schede/resource/CulturalInstituteOrSite/S012166_Teatro_Massimo>

typed as `arco:CulturalInstituteOrSite`

> **Predicate** : `cis:institutionalCISName`

*adds the full official name of the theatre*

>**Object** : "Teatro Massimo Vittorio Emanuele"@it"

*it is a literal with an italian language tag*

---

2️⃣ **RDF Triple for the architects** 

🔍We asked ChatGPT to create a RDF Triple using the **chain-of-thought prompt**


![Screenshot](assets/css/Screenshot%20chat%20prompt%20architects.png) 

It generated the following triple:

```rdf
@prefix arco: <https://w3id.org/arco/ontology/arco/> .
@prefix rdfs: <http://www.w3.org/2000/01/rdf-schema#> .

<http://dati.beniculturali.it/iccd/schede/resource/CulturalInstituteOrSite/S012166_Teatro_Massimo>
    a arco:CulturalInstituteOrSite ;
    arco:hasArchitect <http://dati.beniculturali.it/resource/Person/Giovan_Battista_Filippo_Basile>,
                      <http://dati.beniculturali.it/resource/Person/Ernesto_Basile> .

<http://dati.beniculturali.it/resource/Person/Giovan_Battista_Filippo_Basile>
    a arco:Person ;
    rdfs:label "Giovan Battista Filippo Basile"@it .

<http://dati.beniculturali.it/resource/Person/Ernesto_Basile>
    a arco:Person ;
    rdfs:label "Ernesto Basile"@it .
```

We asked Chat to create it using the following information: 

> **Subject**:Tetaro Massimo di Palermo, IRI <http://dati.beniculturali.it/iccd/schede/resource/CulturalInstituteOrSite/S012166_Teatro_Massimo>

typed as `arco:CulturalInstituteOrSite`

> **Predicate** : `arco:hasArchitect`

*it's the right property to link a cultural institute or site to its architect(s).*

>**Object** : 
<http://dati.beniculturali.it/resource/Person/Giovan_Battista_Filippo_Basile> and <http://dati.beniculturali.it/resource/Person/Ernesto_Basile>

*two architects as separate resources*

---

3️⃣ **RDF Triple for cultural events** 

🔍We asked ChatGPT to create a RDF Triple using a **zero-shot technique**

__

[⬅️ Torna alla home]({{ '/' | relative_url }})
