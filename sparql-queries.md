---
layout: default
title: SPARQL queries
---

# <strong>SPARQL queries<strong>


---
In this section, we examine all the <strong>queries<strong> employed in the study of the <strong>Teatro Massimo di Palermo<strong> within the <strong>ArCo knowledge graph<strong>.

Presented below is an explanation of the **SPARQL keywords** employed in the queries:


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


## Query 1️⃣: checking the presence of Teatro Massimo di Palermo in ArCo
We run a query to check if Teatro Massimo di Palermo was present on ArCo. 

**🔍 Query**:

```sparql
PREFIX rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#>
PREFIX arco: <https://w3id.org/arco/ontology/arco/>
PREFIX rdfs: <http://www.w3.org/2000/01/rdf-schema#>

SELECT DISTINCT ?site ?label
WHERE { 
  ?site a arco:HistoricOrArtisticProperty ;
        rdfs:label ?label .
  FILTER(REGEX(LCASE(STR(?label)), "teatro massimo"))
}
LIMIT 20

```
**📊 Results**:

![Immagine artistic](assets/css/Immagine%20artistic.jpeg)



Using **`arco:HistoricOrArtisticProperty`** as class, we noticed that the results were only artistic representations of the theatre. To find the correct <a href="https://it.wikipedia.org/wiki/Internationalized_Resource_Identifier">IRI</a> of Teatro Massimo, we understood that we had to change class.

## Query 2️⃣: checking the presence of Teatro Massimo di Palermo in ArCo using another class

We changed from **`arco:HistoricOrArtisticProperty`** to **`cis:CulturalInstituteOrSite`**.

**🔍 Query**:

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
LIMIT 20

```

**📊 Results**:

![Immagine arch](assets/css/Immagine%20arch.jpeg)

While the first and the second links refer to “Archivio” and “Biblioteca”, the third link is the correct one for the Teatro Massimo and we identified it as the IRI.

<a href="http://dati.beniculturali.it/iccd/schede/resource/CulturalInstituteOrSite/S012166_Teatro_Massimo"><strong>📍IRI of Teatro Massimo</strong></a> 

We noticed that only very limited information about this theatre was provided. This observation became the starting point of our investigation.


## Query 3️⃣: checking the information of another theatre to compare 
We run the exact same query as Query 2 for other theatres, like the <a href= "https://it.wikipedia.org/wiki/Teatro_Comunale_(Bologna)">Teatro Comunale di Bologna</a>, to compare the results with Teatro Massimo di Palermo and identify possibile gaps.

**🔍 Query**:

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
**📊 Results**:

![Immagine comunale](assets/css/Immagine%20comunale.jpeg)


<a href="http://dati.beniculturali.it/mibact/luoghi/resource/CulturalInstituteOrSite/107941"><strong>📍IRI of Teatro Comunale di Bologna</strong></a> 

In this case, the description was richer compared to Teatro Massimo.

## Query 4️⃣: investigating for the properties in other theatres
Other than comparing to a specific theatre, we checked for the properties generally used to describe a “teatro” in ArCo.

**🔍 Query**:

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
**📊 Results**: 

![Immagine properties](assets/css/Immagine%20properties.jpeg)


The query generated a long list of predicates related to various theatres. We used it as reference. 

## 🔍 Gaps identified
Considering the results of Query 3 and Query 4 the gaps we thought could be added to enrich Teatro Massimo were: 
<ul>
  <li>🏷️ <strong>The full name</strong></li>
  <li>👷‍♂️ <strong>The architects</strong></li>
  <li>🎭 <strong>Events and performances hosted by the theatre</strong></li>
  <li>🛠️ <strong>Restorations and interventions</strong></li>
  <li>🏛️ <strong>Typology of architecture</strong></li>
  <li>🔗 <strong>Wikidata link</strong></li>
  <li>📝 <strong>Description</strong></li>
  <li>📍 <strong>Latitude and longitude</strong></li>
  <li>📷 <strong>Official image</strong></li>
</ul>

    
The next step was to run some queries to ensure these information were actually not present in ArCo.   

## Query 5️⃣: verifying the absence of the full name of the Teatro Massimo  

As part of the enrichment of the ArCo knowledge graph, we submitted a SPARQL query to verify whether it contained information about the full name of the Teatro Massimo in Palermo: **Teatro Massimo Vittorio Emanuele**. This step was aimed at assessing the completeness of the dataset, since the graph often records only the shortened name (Teatro Massimo).

**🔍 Query**:

```sparql
PREFIX rdfs: <http://www.w3.org/2000/01/rdf-schema#>
PREFIX cis: <http://dati.beniculturali.it/cis/>
 
SELECT DISTINCT ?property ?value
WHERE {
  VALUES ?theater {
    <http://dati.beniculturali.it/iccd/schede/resource/CulturalInstituteOrSite/S012166_Teatro_Massimo>
  }
 
  {
	?theater ?property ?value .
  }
  UNION
  {
	?theater ?p ?linkedResource .
	OPTIONAL { ?linkedResource rdfs:label ?value . }
	BIND(?p AS ?property)
  }
 
  FILTER(
    REGEX(LCASE(STR(?value)), "massimo", "i") ||
    REGEX(LCASE(STR(?value)), "emanuele", "i")
  )
}
ORDER BY ?property
LIMIT 50
```

📝 **Analysing the query**:

- **`VALUES`** → specifies the theatre we are querying, setting the Teatro Massimo IRI as the subject.
- **`?theater ?property ?value`** → retrieves all direct properties and their corresponding values of the theater.
- **`OPTIONAL`** → retrieves rdfs:label and cis:institutionalCISName if they exist, but the query will not fail if they are missing.
- **`SELECT`** → specifies which variables are returned.
- **`FILTER + REGEX`** → filters results for values containing “massimo” or “emanuele” (case-insensitive).
- **`ORDER BY ?property`** → sorts results by property.
- **`LIMIT 50`** → limits the results to 50 rows.
    
 

**📊 Results**: 

<a href = "https://dati.cultura.gov.it/sparql?default-graph-uri=&query=PREFIX+rdfs%3A+%3Chttp%3A%2F%2Fwww.w3.org%2F2000%2F01%2Frdf-schema%23%3E%0D%0APREFIX+cis%3A+%3Chttp%3A%2F%2Fdati.beniculturali.it%2Fcis%2F%3E%0D%0A+%0D%0ASELECT+DISTINCT+%3Fproperty+%3Fvalue%0D%0AWHERE+%7B%0D%0A++VALUES+%3Ftheater+%7B%0D%0A++++%3Chttp%3A%2F%2Fdati.beniculturali.it%2Ficcd%2Fschede%2Fresource%2FCulturalInstituteOrSite%2FS012166_Teatro_Massimo%3E%0D%0A++%7D%0D%0A+%0D%0A++%7B%0D%0A%09%3Ftheater+%3Fproperty+%3Fvalue+.%0D%0A++%7D%0D%0A++UNION%0D%0A++%7B%0D%0A%09%3Ftheater+%3Fp+%3FlinkedResource+.%0D%0A%09OPTIONAL+%7B+%3FlinkedResource+rdfs%3Alabel+%3Fvalue+.+%7D%0D%0A%09BIND%28%3Fp+AS+%3Fproperty%29%0D%0A++%7D%0D%0A+%0D%0A++FILTER%28%0D%0A++++REGEX%28LCASE%28STR%28%3Fvalue%29%29%2C+%22massimo%22%2C+%22i%22%29+%7C%7C%0D%0A++++REGEX%28LCASE%28STR%28%3Fvalue%29%29%2C+%22emanuele%22%2C+%22i%22%29%0D%0A++%29%0D%0A%7D%0D%0AORDER+BY+%3Fproperty%0D%0ALIMIT+50%0D%0A&format=text%2Fhtml&timeout=0&signal_void=on"> ❌ Table</a> 

The query confirmed that ArCo does not contain the property that we seeked. 


## Query 6️⃣: verifying the absence of the architects
To support the enrichment of the ArCo knowledge graph, we formulated a SPARQL query to investigate whether information about the **architects** of the Teatro Massimo in Palermo was already available. This step aimed to evaluate the coverage of the dataset regarding key contributors to the theatre’s design.

**🔍 Query**:

```sparql
PREFIX arco: <https://w3id.org/arco/ontology/arco/>
PREFIX rdfs: <http://www.w3.org/2000/01/rdf-schema#>
 
SELECT DISTINCT ?architect ?architectLabel
WHERE {
  VALUES ?theatre {
    <http://dati.beniculturali.it/iccd/schede/resource/CulturalInstituteOrSite/S012166_Teatro_Massimo>
  }
 

  OPTIONAL {
	?theatre arco:hasArchitect ?architect .
	OPTIONAL { ?architect rdfs:label ?architectLabel . }
  }
 

  FILTER(
    !BOUND(?architectLabel) ||
    REGEX(LCASE(STR(?architectLabel)), "basile", "i")
  )
}
ORDER BY ?architectLabel
LIMIT 10


```
📝 **Analysing the query**:

- **`DISTINCT`** → avoids duplicate architects if linked multiple times.
- **`VALUES`** → sets Teatro Massimo as the subject.
- **`FILTER + REGEX`** → filters results to include only architects whose label contains “basile” (case-insensitive).
- **`OPTIONAL`** → optionally retrieves the architect linked to the theater and, if available, the architect’s label. The query does not fail if this information is missing.
- **`ORDER BY`** → sorts the results alphabetically by name.



**📊 Results**: 

<a href="https://dati.cultura.gov.it/sparql?default-graph-uri=&query=PREFIX+arco%3A+%3Chttps%3A%2F%2Fw3id.org%2Farco%2Fontology%2Farco%2F%3E%0D%0APREFIX+rdfs%3A+%3Chttp%3A%2F%2Fwww.w3.org%2F2000%2F01%2Frdf-schema%23%3E%0D%0A+%0D%0ASELECT+DISTINCT+%3Farchitect+%3FarchitectLabel%0D%0AWHERE+%7B%0D%0A++VALUES+%3Ftheatre+%7B%0D%0A++++%3Chttp%3A%2F%2Fdati.beniculturali.it%2Ficcd%2Fschede%2Fresource%2FCulturalInstituteOrSite%2FS012166_Teatro_Massimo%3E%0D%0A++%7D%0D%0A+%0D%0A%0D%0A++OPTIONAL+%7B%0D%0A%09%3Ftheatre+arco%3AhasArchitect+%3Farchitect+.%0D%0A%09OPTIONAL+%7B+%3Farchitect+rdfs%3Alabel+%3FarchitectLabel+.+%7D%0D%0A++%7D%0D%0A+%0D%0A%0D%0A++FILTER%28%0D%0A++++%21BOUND%28%3FarchitectLabel%29+%7C%7C%0D%0A++++REGEX%28LCASE%28STR%28%3FarchitectLabel%29%29%2C+%22basile%22%2C+%22i%22%29%0D%0A++%29%0D%0A%7D%0D%0AORDER+BY+%3FarchitectLabel%0D%0ALIMIT+10&format=text%2Fhtml&timeout=0&signal_void=on">❌ Table</a>

The query confirmed that ArCo does contain the property that we seeked. 


## Query 7️⃣: verifying the absence of events and performances hosted by teatro massimo 
In continuity with the previous steps, we also created a SPARQL query to interrogate the ArCo knowledge graph about the **events and performances** hosted by the Teatro Massimo in Palermo. The aim was to verify whether the dataset already documented the wide range of cultural activities associated with the theatre, such as opera productions, concerts, ballet, and festivals.

**🔍 Query**:

```sparql

PREFIX arco: <https://w3id.org/arco/ontology/arco/>
PREFIX rdfs: <http://www.w3.org/2000/01/rdf-schema#>
 
SELECT DISTINCT ?activity ?activityLabel
WHERE {
  VALUES ?theatre {
    <http://dati.beniculturali.it/iccd/schede/resource/CulturalInstituteOrSite/S012166_Teatro_Massimo>
  }
 
  {
	OPTIONAL {
  	?theatre arco:hasActivity ?activity .
  	OPTIONAL { ?activity rdfs:label ?activityLabel . }
	}
  }
  UNION
  {
	OPTIONAL {
  	?theatre arco:hasEvent ?activity .
  	OPTIONAL { ?activity rdfs:label ?activityLabel . }
	}
  }
 
  FILTER(
    !BOUND(?activityLabel) ||
    REGEX(LCASE(STR(?activityLabel)), "opera|concert|ballet|show", "i")
  )
}
ORDER BY ?activityLabel
LIMIT 50
```
📝 **Analysing the query**:


- **`OPTIONAL`** → optionally retrieves activities linked directly to the theater via **`arco:hasActivity`**, and if available, also retrieves the label of each activity. The query does not fail if this information is missing.
- **`OPTIONAL`** → optionally retrieves events linked to the theater via **`arco:hasEvent`**, and if available, also retrieves their label. Again, the query does not fail if this information is missing.
- **`FILTER + REGEX`** → restricts results to labels containing opera, ballet, concert, or festival (case-insensitive).



**📊 Results**: 

<a href="https://dati.cultura.gov.it/sparql?default-graph-uri=&query=PREFIX+arco%3A+%3Chttps%3A%2F%2Fw3id.org%2Farco%2Fontology%2Farco%2F%3E%0D%0APREFIX+rdfs%3A+%3Chttp%3A%2F%2Fwww.w3.org%2F2000%2F01%2Frdf-schema%23%3E%0D%0A+%0D%0ASELECT+DISTINCT+%3Factivity+%3FactivityLabel%0D%0AWHERE+%7B%0D%0A++VALUES+%3Ftheatre+%7B%0D%0A++++%3Chttp%3A%2F%2Fdati.beniculturali.it%2Ficcd%2Fschede%2Fresource%2FCulturalInstituteOrSite%2FS012166_Teatro_Massimo%3E%0D%0A++%7D%0D%0A+%0D%0A++%7B%0D%0A%09OPTIONAL+%7B%0D%0A++%09%3Ftheatre+arco%3AhasActivity+%3Factivity+.%0D%0A++%09OPTIONAL+%7B+%3Factivity+rdfs%3Alabel+%3FactivityLabel+.+%7D%0D%0A%09%7D%0D%0A++%7D%0D%0A++UNION%0D%0A++%7B%0D%0A%09OPTIONAL+%7B%0D%0A++%09%3Ftheatre+arco%3AhasEvent+%3Factivity+.%0D%0A++%09OPTIONAL+%7B+%3Factivity+rdfs%3Alabel+%3FactivityLabel+.+%7D%0D%0A%09%7D%0D%0A++%7D%0D%0A+%0D%0A++FILTER%28%0D%0A++++%21BOUND%28%3FactivityLabel%29+%7C%7C%0D%0A++++REGEX%28LCASE%28STR%28%3FactivityLabel%29%29%2C+%22opera%7Cconcert%7Cballet%7Cshow%22%2C+%22i%22%29%0D%0A++%29%0D%0A%7D%0D%0AORDER+BY+%3FactivityLabel%0D%0ALIMIT+50&format=text%2Fhtml&timeout=0&signal_void=on"> ❌ Table</a>

The results showed blank spaces. 

## Query 8️⃣: verifying the absence of restorations and interventions carried out on the Teatro Massimo
As a final step, we designed a SPARQL query to interrogate the ArCo knowledge graph about the restorations and interventions carried out on the Teatro Massimo in Palermo. The goal was to assess whether the dataset already included references to the theatre’s complex conservation history, which spans closures, structural works, and reopening phases.

**🔍 Query**:

```sparql

PREFIX arco: <https://w3id.org/arco/ontology/arco/>
PREFIX rdfs: <http://www.w3.org/2000/01/rdf-schema#>
 
SELECT DISTINCT ?intervention ?interventionLabel
WHERE {
  VALUES ?theatre {
    <http://dati.beniculturali.it/iccd/schede/resource/CulturalInstituteOrSite/S012166_Teatro_Massimo>
  }
 
  {
	OPTIONAL {
  	?theatre arco:hasIntervention ?intervention .
  	OPTIONAL { ?intervention rdfs:label ?interventionLabel . }
	}
  }
  UNION
  {

	OPTIONAL {
  	?theatre arco:restoration ?interventionLabel .
  	BIND(?theatre AS ?intervention)
	}
  }
 
  FILTER(
    !BOUND(?interventionLabel) ||
    REGEX(LCASE(STR(?interventionLabel)), "restoration|restauro|intervention|consolidation", "i")
  )
}
ORDER BY ?interventionLabel
LIMIT 50



```
📝 **Analysing the query**:

- **`OPTIONAL`** → optionally retrieves interventions linked to the theater via **`arco:Intervention`**, and if available, also retrieves the label (rdfs:label) of each intervention. The query does not fail if this information is missing.
- **`OPTIONAL`** → optionally retrieves restoration descriptions linked to the theater via **`arco:Restoration`**. It also binds the theater itself to ?intervention so the variable is always defined.
- **`FILTER + REGEX`** → filters results to include only labels containing “restoration”, “restauro”, “intervention”, or “consolidation” (case-insensitive), or allows results where the label is not defined.



**📊 Results**: 

<a href="https://dati.cultura.gov.it/sparql?default-graph-uri=&query=PREFIX+arco%3A+%3Chttps%3A%2F%2Fw3id.org%2Farco%2Fontology%2Farco%2F%3E%0D%0APREFIX+rdfs%3A+%3Chttp%3A%2F%2Fwww.w3.org%2F2000%2F01%2Frdf-schema%23%3E%0D%0A+%0D%0ASELECT+DISTINCT+%3Fintervention+%3FinterventionLabel%0D%0AWHERE+%7B%0D%0A++VALUES+%3Ftheatre+%7B%0D%0A++++%3Chttp%3A%2F%2Fdati.beniculturali.it%2Ficcd%2Fschede%2Fresource%2FCulturalInstituteOrSite%2FS012166_Teatro_Massimo%3E%0D%0A++%7D%0D%0A+%0D%0A++%7B%0D%0A%09OPTIONAL+%7B%0D%0A++%09%3Ftheatre+arco%3AhasIntervention+%3Fintervention+.%0D%0A++%09OPTIONAL+%7B+%3Fintervention+rdfs%3Alabel+%3FinterventionLabel+.+%7D%0D%0A%09%7D%0D%0A++%7D%0D%0A++UNION%0D%0A++%7B%0D%0A%0D%0A%09OPTIONAL+%7B%0D%0A++%09%3Ftheatre+arco%3Arestoration+%3FinterventionLabel+.%0D%0A++%09BIND%28%3Ftheatre+AS+%3Fintervention%29%0D%0A%09%7D%0D%0A++%7D%0D%0A+%0D%0A++FILTER%28%0D%0A++++%21BOUND%28%3FinterventionLabel%29+%7C%7C%0D%0A++++REGEX%28LCASE%28STR%28%3FinterventionLabel%29%29%2C+%22restoration%7Crestauro%7Cintervention%7Cconsolidation%22%2C+%22i%22%29%0D%0A++%29%0D%0A%7D%0D%0AORDER+BY+%3FinterventionLabel%0D%0ALIMIT+50&format=text%2Fhtml&timeout=0&signal_void=on"> ❌ Table</a>

Again, the results showed blank spaces.


## Query 9️⃣: verifying the absence of the type of architecture

Taking into account the example of Teatro comunale di Bologna, we found the description “architettura civile” under the property **`DC:Type`**. We ran a SPARQL query to check if this property was present on ArCo for the Teatro Massimo di Palermo. 


**🔍 Query**:

```sparql

PREFIX dc: <http://purl.org/dc/terms/>
PREFIX rdfs: <http://www.w3.org/2000/01/rdf-schema#>

SELECT DISTINCT ?type ?label
WHERE {
  {
    <http://dati.beniculturali.it/iccd/schede/resource/CulturalInstituteOrSite/S012166_Teatro_Massimo> dc:type ?type .
    OPTIONAL { ?type rdfs:label ?label . }
  }
  UNION
  {
    <http://dati.beniculturali.it/iccd/schede/resource/CulturalInstituteOrSite/S012166_Teatro_Massimo> dc:type ?type .
    FILTER(REGEX(STR(?type), "architettura|teatro", "i"))
    OPTIONAL { ?type rdfs:label ?label . }
  }
}
ORDER BY ?label
LIMIT 10

```
📝 **Analysing the query**:

- **`dc:type`** - **`rdfs:label`** → This query retrieves the distinct types associated with the Teatro Massimo di Palermo resource, along with their optional labels.

- **`FILTER + REGEX`** → filters the types to include only those containing the words “architettura” or “teatro” (case-insensitive).

- **`ORDER BY ?label`** → sorts the results alphabetically by label.


**📊 Results**: 

<a href= "https://dati.cultura.gov.it/sparql?default-graph-uri=&query=PREFIX+dc%3A+%3Chttp%3A%2F%2Fpurl.org%2Fdc%2Fterms%2F%3E%0D%0APREFIX+rdfs%3A+%3Chttp%3A%2F%2Fwww.w3.org%2F2000%2F01%2Frdf-schema%23%3E%0D%0A%0D%0ASELECT+DISTINCT+%3Ftype+%3Flabel%0D%0AWHERE+%7B%0D%0A++%7B%0D%0A++++%3Chttp%3A%2F%2Fdati.beniculturali.it%2Ficcd%2Fschede%2Fresource%2FCulturalInstituteOrSite%2FS012166_Teatro_Massimo%3E+dc%3Atype+%3Ftype+.%0D%0A++++OPTIONAL+%7B+%3Ftype+rdfs%3Alabel+%3Flabel+.+%7D%0D%0A++%7D%0D%0A++UNION%0D%0A++%7B%0D%0A++++%3Chttp%3A%2F%2Fdati.beniculturali.it%2Ficcd%2Fschede%2Fresource%2FCulturalInstituteOrSite%2FS012166_Teatro_Massimo%3E+dc%3Atype+%3Ftype+.%0D%0A++++FILTER%28REGEX%28STR%28%3Ftype%29%2C+%22architettura%7Cteatro%22%2C+%22i%22%29%29%0D%0A++++OPTIONAL+%7B+%3Ftype+rdfs%3Alabel+%3Flabel+.+%7D%0D%0A++%7D%0D%0A%7D%0D%0AORDER+BY+%3Flabel%0D%0ALIMIT+10%0D%0A%0D%0A&format=text%2Fhtml&timeout=0&signal_void=on"> ❌ Table </a>

This query showed no results.

## Query 1️⃣0️⃣: verifying the absence of the wikidata link

**🔍 Query**:

```sparql

```

📝 **Analysing the query**:

**📊 Results**: 

## Query 1️⃣1️⃣: verifying the absence of the architectural description

**🔍 Query**:

```sparql

```


📝 **Analysing the query**:

**📊 Results**: 

## Query 1️⃣2️⃣: verifying the absence of the latitude and longitude

**🔍 Query**:

```sparql

```

📝 **Analysing the query**:

**📊 Results**: 

## Query 1️⃣3️⃣: verifying the absence of the official image

**🔍 Query**:

```sparql

```

📝 **Analysing the query**:

**📊 Results**: 

[⬅️ Torna alla home]({{ '/' | relative_url }})
