---
layout: default
title: SPARQL queries
---

# <strong>SPARQL queries<strong>


---
## 1) Checking the presence of Teatro Massimo di Palermo in ArCo
One of the theatres we checked was Teatro Massimo di Palermo:

```sparql
PREFIX rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#>
 PREFIX arco: <https://w3id.org/arco/ontology/arco/>
 PREFIX a-cd: <https://w3id.org/arco/ontology/context-description/>

 SELECT DISTINCT ?cp
 WHERE {
 ?cp a arco:HistoricOrArtisticProperty ;
 rdfs:label ?l .
 FILTER(REGEX(?l, "Abbazia di Nonantola", "i")
 }
```

Benvenuto nella pagina SPARQL queries.

_Testo di esempio…_

[⬅️ Torna alla home]({{ '/' | relative_url }})
