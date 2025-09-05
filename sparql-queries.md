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
**📊 Results**

While the first and the second links refer to “Archivio” and “Biblioteca”, the third link is the correct one for the Teatro Massimo and we identified it as the IRI. 
We noticed that for Teatro Massimo in Palermo only very limited information was provided. This observation became the starting point of our investigation.


## 2️⃣ Checking the information of another theatre to compare 
We run the exact same query as Query 1 for other theatres, like the Teatro Comunale di Bologna, to compare the results with Teatro Massimo di Palermo and identify possibile gaps: 

```sparql
PREFIX rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#>
PREFIX cis: <http://dati.beniculturali.it/cis/>
PREFIX rdfs: <http://www.w3.org/2000/01/rdf-schema#>

SELECT DISTINCT ?site ?label
WHERE { 
  ?site a cis:CulturalInstituteOrSite ;
        rdfs:label ?label .
  FILTER(REGEX(LCASE(STR(?label)), "teatro comunale di Bologna"))
}


```
**📊 Results**
In this case, the description was richer compared to Teatro Massimo.

## 3️⃣ Investigating for the properties in other theatres
Other than comparing to a specific theatre, we checked for the properties generally used to describe a “teatro” in ArCo:

```sparql
PREFIX rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#> 
PREFIX arco: <https://w3id.org/arco/ontology/arco/> 
PREFIX a-cd: <https://w3id.org/arco/ontology/context-description/>
PREFIX cis: <http://dati.beniculturali.it/cis/> 

SELECT DISTINCT ?property ?value 
WHERE {  
  ?entity a cis:CulturalInstituteOrSite ;
      rdfs:label ?l ; 
      ?property ?value .  
  FILTER(REGEX(?l, "teatro", "i"))  
}  
ORDER BY DESC(?property)



```
**📊 Results** 
The query generated a long list of predicates related to various theatres. We used it as reference. 

**🔍 Gaps identified**
<ul>
  <li>📛 The full name</li>
  <li👷‍♂️> The architects</li>
  <li>🎭 Events and performances hosted by the theatre</li>
  <li>🛠️ Restorations and interventions</li>
  <li>🏛️ Typology of architecture</li>
  <li>🔗 Wikidata link</li>
  <li>📝 Description</li>
  <li>📍 Latitude and longitude</li>
  <li>📷 Photo</li>
</ul>


_Testo di esempio…_

[⬅️ Torna alla home]({{ '/' | relative_url }})
