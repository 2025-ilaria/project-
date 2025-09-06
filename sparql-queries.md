---
layout: default
title: SPARQL queries
---

# <strong>SPARQL queries<strong>


---
In this section, we examine all the <strong>queries<strong> employed in the study of the <strong>Teatro Massimo di Palermo<strong> within the <strong>ArCo knowledge graph<strong>.

Presented below is an explanation of the SPARQL keywords employed in the queries:


<h2>SPARQL Keywords Explained</h2>

<table style="width:100%;border-collapse:collapse;font-family:Arial,Helvetica,sans-serif;">
  <thead>
    <tr>
      <th style="background:#e0f7e9;text-align:left;padding:8px;width:18%;">Keyword</th>
      <th style="background:#e0f7e9;text-align:left;padding:8px;">Explanation</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="padding:8px;font-weight:700;">DISTINCT</td>
      <td style="padding:8px;border-bottom:1px solid #ddd;">Ensures that the results returned are unique (no duplicates).</td>
    </tr>
    <tr>
      <td style="padding:8px;font-weight:700;">FILTER</td>
      <td style="padding:8px;border-bottom:1px solid #ddd;">Restricts the results to those that satisfy a certain condition.</td>
    </tr>
    <tr>
      <td style="padding:8px;font-weight:700;">REGEX</td>
      <td style="padding:8px;border-bottom:1px solid #ddd;">A type of filter for matching text using regular expressions.</td>
    </tr>
    <tr>
      <td style="padding:8px;font-weight:700;">OPTIONAL</td>
      <td style="padding:8px;border-bottom:1px solid #ddd;">Includes extra information if available, without excluding results when data is missing.</td>
    </tr>
    <tr>
      <td style="padding:8px;font-weight:700;">UNION</td>
      <td style="padding:8px;border-bottom:1px solid #ddd;">Combines results from multiple query patterns.</td>
    </tr>
    <tr>
      <td style="padding:8px;font-weight:700;">LIMIT</td>
      <td style="padding:8px;border-bottom:1px solid #ddd;">Restricts the maximum number of results returned by the query.</td>
    </tr>
    <tr>
      <td style="padding:8px;font-weight:700;">ORDER BY</td>
      <td style="padding:8px;border-bottom:1px solid #ddd;">Sorts results by a variable.</td>
    </tr>
  </tbody>
</table>


## Query 1️⃣: Checking the presence of Teatro Massimo di Palermo in ArCo
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


## Query 2️⃣: Checking the information of another theatre to compare 
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

## Query 3️⃣: Investigating for the properties in other theatres
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

## 🔍 Gaps identified
Considering the results of Query 2 and Query 3 the gaps we think can be added to enrich Teatro Massimo are: 
<ul>
  <li>🏷️ <strong>The full name<strong></li>
  <li>👷‍♂️ <strong>The architects<strong></li>
  <li>🎭 <strong>Events and performances hosted by the theatre<strong></li>
  <li>🛠️ <strong>Restorations and interventions<strong></li>
  <li>🏛️ <strong>Typology of architecture<strong></li>
  <li>🔗 <strong>Wikidata link<strong></li>
  <li>📝 <strong>Description<strong></li>
  <li>📍 <strong>Latitude and longitude<strong></li>
  <li>📷 <strong>Official Photo<strong></li>
</ul>
Then we run some queries to ensure these information were actually not present in ArCo.

## Query 🔍:

_Testo di esempio…_

[⬅️ Torna alla home]({{ '/' | relative_url }})
