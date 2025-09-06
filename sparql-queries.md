---
layout: default
title: SPARQL queries
---

# <strong>SPARQL queries<strong>


---
In this section, we examine all the <strong>queries<strong> employed in the study of the <strong>Teatro Massimo di Palermo<strong> within the <strong>ArCo knowledge graph<strong>.

Presented below is an explanation of the SPARQL keywords employed in the queries:

```html
<h2>SPARQL Keywords Explained</h2>

<table border="1" cellpadding="8" cellspacing="0" style="border-collapse: collapse; width: 100%; font-family: Arial, sans-serif;">
  <thead style="background-color: #e0f7e9;">
    <tr>
      <th style="text-align: left;">Keyword</th>
      <th style="text-align: left;">Explanation</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><b>DISTINCT</b></td>
      <td>Removes duplicate results from the query output, ensuring each row is unique.</td>
    </tr>
    <tr>
      <td><b>FILTER</b></td>
      <td>Restricts results based on conditions (e.g., only labels in English).</td>
    </tr>
    <tr>
      <td><b>REGEX</b></td>
      <td>A type of filter for matching text using regular expressions (e.g., find labels containing "teatro massimo").</td>
    </tr>
    <tr>
      <td><b>OPTIONAL</b></td>
      <td>Includes extra information if available, without excluding results when data is missing.</td>
    </tr>
    <tr>
      <td><b>UNION</b></td>
      <td>Combines results from multiple patterns (logical OR between graph patterns).</td>
    </tr>
    <tr>
      <td><b>LIMIT</b></td>
      <td>Restricts the maximum number of results returned by the query.</td>
    </tr>
    <tr>
      <td><b>ORDER BY</b></td>
      <td>Sorts results by a variable, either ascending (default) or descending.</td>
    </tr>
  </tbody>
</table>
```

✨ This will generate a **green-tinted header table** with two columns:

* *Keyword*
* *Explanation*

Do you also want me to **add an example query row** for each keyword (like mini code snippets), or keep it as plain explanations?


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
