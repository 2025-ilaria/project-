---
layout: default
title: RDF Triples
---

# RDF Triples


---

In this section there are all **RDF Triples** generated for each gap.  

# RDF Triple Full Name 
We asked CHAT GPT to create a triple using the **zero-shot prompt**:

![Screenshot](https://github.com/2025-ilaria/project-/blob/master/assets/css/Screenshot%20Chat%20prompt%20name%20triple.png)

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

> **Subject**:[<http://dati.beniculturali.it/iccd/schede/resource/CulturalInstituteOrSite/S012166_Teatro_Massimo>]
typed as `arco:CulturalInstituteOrSite`

> **Predicate** : `cis:institutionalCISName`
*adds the full official name of the theatre*

>**Object** : "Teatro Massimo Vittorio Emanuele"@it"
*is a literal with an italian language tag*


__

[⬅️ Torna alla home]({{ '/' | relative_url }})
