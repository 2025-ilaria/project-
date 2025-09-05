---
layout: default
title: SPARQL queries
---

# <strong>SPARQL queries<strong>


---
## 1️⃣ Checking the presence of Teatro Massimo di Palermo in ArCo
One of the theatres we checked was Teatro Massimo di Palermo:

```sparql
PREFIX rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#>
PREFIX cis: <http://dati.beniculturali.it/cis/>
PREFIX rdfs: <http://www.w3.org/2000/01/rdf-schema#>

SELECT DISTINCT ?site ?label
WHERE { 
  ?site a cis:CulturalInstituteOrSite ;
        rdfs:label ?label .
  FILTER(REGEX(LCASE(STR(?label)), "teatro massimo"))
}

```

Benvenuto nella pagina SPARQL queries.

_Testo di esempio…_

[⬅️ Torna alla home]({{ '/' | relative_url }})
