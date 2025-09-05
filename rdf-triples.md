---
layout: default
title: RDF Triples
---

# **RDF Triples**

In this section there are all **RDF Triples** generated for each gap.  

---
1️⃣ **RDF Triple Full Name** 

🔍We asked CHAT GPT to create a triple using the **zero-shot prompt**

![Screenshot](assets/css/Screenshot%20Chat%20prompt%20name%20triple.png)

Here the result ➡️

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

It generated the following triple ➡️

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

> **Subject**:Teatro Massimo di Palermo, IRI <http://dati.beniculturali.it/iccd/schede/resource/CulturalInstituteOrSite/S012166_Teatro_Massimo>

typed as `arco:CulturalInstituteOrSite`

> **Predicate** : `arco:hasArchitect`

*it's the right property to link a cultural institute or site to its architect(s).*

>**Object** : 
<http://dati.beniculturali.it/resource/Person/Giovan_Battista_Filippo_Basile> and <http://dati.beniculturali.it/resource/Person/Ernesto_Basile>

*two architects as separate resources*

---
3️⃣ **RDF Triple for cultural events** 

🔍We asked ChatGPT to create a RDF Triple using a **zero-shot technique**:

![Screenshot](assets/css/Screenshot%20triple%20prompt%20cultural%20events.png)

It generated the following triple➡️

```rdf
@prefix arco: <https://w3id.org/arco/ontology/arco/> .
@prefix rdfs: <http://www.w3.org/2000/01/rdf-schema#> .
@prefix ex: <http://example.org/resource/Event/> .

# Teatro Massimo as a Cultural Institute or Site
<http://dati.beniculturali.it/iccd/schede/resource/CulturalInstituteOrSite/S012166_Teatro_Massimo>
    a arco:CulturalInstituteOrSite ;
    rdfs:label "Teatro Massimo"@it ;
    arco:hasEvent ex:OperaProduction ;
    arco:hasEvent ex:TheaterPerformance ;
    arco:hasEvent ex:OrchestralConcert ;
    arco:hasEvent ex:BalletDance ;
    arco:hasEvent ex:FestivalEvent .

# Define each event as a Cultural Event resource
ex:OperaProduction
    a arco:Event ;
    rdfs:label "Opera production"@en .

ex:TheaterPerformance
    a arco:Event ;
    rdfs:label "Theater performances"@en .

ex:OrchestralConcert
    a arco:Event ;
    rdfs:label "Orchestral concerts"@en .

ex:BalletDance
    a arco:Event ;
    rdfs:label "Ballet dance"@en .

ex:FestivalEvent
    a arco:Event ;
    rdfs:label "Festival events"@en .
```

📝Then we asked if it could add some information provided previously and it gave this triple ➡️

```rdf
@prefix arco: <https://w3id.org/arco/ontology/arco/> .
@prefix rdfs: <http://www.w3.org/2000/01/rdf-schema#> .
@prefix ex: <http://example.org/resource/Event/> .

# Teatro Massimo as a Cultural Institute or Site
<http://dati.beniculturali.it/iccd/schede/resource/CulturalInstituteOrSite/S012166_Teatro_Massimo>
    a arco:CulturalInstituteOrSite ;
    rdfs:label "Teatro Massimo"@it ;
    arco:hasEvent ex:OperaProduction ;
    arco:hasEvent ex:TheaterPerformance ;
    arco:hasEvent ex:OrchestralConcert ;
    arco:hasEvent ex:BalletDance ;
    arco:hasEvent ex:FestivalEvent .

# Define each event as a Cultural Event resource with additional info
ex:OperaProduction
    a arco:Event ;
    rdfs:label "Opera production"@en ;
    rdfs:comment "Includes classic and contemporary operas such as Il barbiere di Siviglia, I Capuleti e i Montecchi, Rigoletto, and Madama Butterfly, with notable conductors and directors."@en .

ex:TheaterPerformance
    a arco:Event ;
    rdfs:label "Theater performances"@en ;
    rdfs:comment "Dramatic plays and musical theater productions staged at the venue, featuring both Italian and international works."@en .

ex:OrchestralConcert
    a arco:Event ;
    rdfs:label "Orchestral concerts"@en ;
    rdfs:comment "Concerts including orchestral, choral, and chamber music performed by the Teatro Massimo Orchestra and Chorus, including the annual New Year's Concert."@en .

ex:BalletDance
    a arco:Event ;
    rdfs:label "Ballet dance"@en ;
    rdfs:comment "Classical and contemporary ballet performances, including narrative ballets such as Franca Florio, regina di Palermo premiered in 2007."@en .

ex:FestivalEvent
    a arco:Event ;
    rdfs:label "Festival events"@en ;
    rdfs:comment "Seasonal festivals and special cultural events, including the Summer Programme at Teatro di Verdura and educational outreach programs such as Massimo's Young Musicians and Children at the Opera."@en .
```

We asked Chat to create it using the following information:

>**Subject**: Teatro Massimo di Palermo, IRI <http://dati.beniculturali.it/iccd/schede/resource/CulturalInstituteOrSite/S012166_Teatro_Massimo>

>**Predicate**: `arco:hasEvent`

>**Object**: ex:OperaProduction, ex:TheaterPerformance, ex:OrchestralConcert, ex:BalletDance, ex:FestivalEvent

---
4️⃣**RDF Triple for restoration and intervention**

🔍We asked CHAT GPT to create a RDF triple using the **zero-shot prompt**: 

![Screnshot](assets/css/Screenshot%20prompt%20restoration%20triple.png)

It generated the following triple➡️

```rdf
@prefix arco: <https://w3id.org/arco/ontology/arco/> .
@prefix rdfs: <http://www.w3.org/2000/01/rdf-schema#> .

<http://dati.beniculturali.it/iccd/schede/resource/CulturalInstituteOrSite/S012166_Teatro_Massimo>
    a arco:CulturalInstituteOrSite ;
    arco:hasIntervention <http://dati.beniculturali.it/resource/Intervention/TeatroMassimo_1974_1975> ,
                         <http://dati.beniculturali.it/resource/Intervention/TeatroMassimo_1975_1980s> ,
                         <http://dati.beniculturali.it/resource/Intervention/TeatroMassimo_1980s_1997> .

<http://dati.beniculturali.it/resource/Intervention/TeatroMassimo_1974_1975>
    a arco:Intervention ;
    rdfs:label "Closure and initial surveys for restoration (1974–1975)"@en .

<http://dati.beniculturali.it/resource/Intervention/TeatroMassimo_1975_1980s>
    a arco:Intervention ;
    rdfs:label "Structural consolidation and interior restoration (late 1970s–1980s)"@en .

<http://dati.beniculturali.it/resource/Intervention/TeatroMassimo_1980s_1997>
    a arco:Intervention ;
    rdfs:label "Reopening and modernization completed (1980s–1997)"@en .
```
We asked Chat to create it using the following information:

> **Subject:**  Teatro Massimo di Palermo, IRI <http://dati.beniculturali.it/iccd/schede/resource/CulturalInstituteOrSite/S012166_Teatro_Massimo>.   
> **Predicate:** `arco:hasIntervention`   
> **Object:** Intervention/TeatroMassimo_1974_1975, etc.

➡️Subject: typed as `arco:CulturalInstituteOrSite`.
➡️Predicate: it links the theatre to three distinct restoration interventions.
➡️Object: It is declared as `arco:hasIntervention` and provided with `rdfs:label` describing the intervention.

---
5️⃣ **RDF Triple for type of architecture**

🔍Using a **zero-shot prompt technique**, we asked ChatGPT to create a RDF Triple:

![Screenshot](assets/css/Screenshot%20prompt%20dc%20type%20triple.png)

Here the result➡️

```rdf
@prefix dc: <http://purl.org/dc/terms/> .
@prefix arco: <https://w3id.org/arco/ontology/core/> .
@prefix rdfs: <http://www.w3.org/2000/01/rdf-schema#> .

<http://dati.beniculturali.it/iccd/schede/resource/CulturalInstituteOrSite/S012166_Teatro_Massimo>
    rdfs:label "Teatro Massimo Vittorio Emanuele, Palermo"@it ;
    dc:type "architettura civile"@it .
```
---
We asked Chat to create it using the following information: 

> **Subject:**  Teatro Massimo di Palermo, IRI <http://dati.beniculturali.it/iccd/schede/resource/CulturalInstituteOrSite/S012166_Teatro_Massimo>.   
> **Predicate:** `dc:type`   
> **Object:** architettura civile.

---
6️⃣**RDF Triple for wikidata link**

🔍Using a **zero-shot prompt technique**, we asked ChatGPT to create a RDF Triple:

![Screnshot](assets/css/Screenshot%20wikida%20triple%20prompt.png)

Here the result➡️

```rdf
@prefix owl: <http://www.w3.org/2002/07/owl#> .
@prefix rdfs: <http://www.w3.org/2000/01/rdf-schema#> .
@prefix arco: <https://w3id.org/arco/ontology/core/> .

<http://dati.beniculturali.it/iccd/schede/resource/CulturalInstituteOrSite/S012166_Teatro_Massimo>
    rdfs:label "Teatro Massimo Vittorio Emanuele, Palermo"@it ;
    owl:sameAs <https://www.wikidata.org/entity/Q261439> .
```

We asked Chat to create it using the following information:

> **Subject:**  Teatro Massimo di Palermo, IRI <http://dati.beniculturali.it/iccd/schede/resource/CulturalInstituteOrSite/S012166_Teatro_Massimo>.   
> **Predicate:** `owl:sameAs`   
> **Object:** <https://www.wikidata.org/entity/Q261439>. 

---
7️⃣**RDF Triple for description**

🔍Using a **zero-shot prompt technique**, we asked ChatGPT to create a RDF Triple:

![Screenshot](assets/css/Screenshot%20prompt%20descrp%20triple.png)

Here the result➡️

```rdf
@prefix l0: <https://w3id.org/italia/onto/l0/> .
@prefix rdfs: <http://www.w3.org/2000/01/rdf-schema#> .
@prefix xsd: <http://www.w3.org/2001/XMLSchema#> .

<http://dati.beniculturali.it/iccd/schede/resource/CulturalInstituteOrSite/S012166_Teatro_Massimo>
    l0:description """It features Neoclassical architecture enriched with Eclectic and early Art Nouveau (Liberty) influences. The exterior includes a grand staircase leading to a portico supported by six Corinthian columns. Two bronze lions guard the entrance, symbolizing tragedy and lyric poetry. The dome, made of iron and bronze, spans 28.7 meters and includes a mechanism to adapt to thermal expansion. The auditorium, in a horseshoe shape, accommodates around 1,300–1,400 spectators across five tiers and a gallery. It is celebrated for its perfect acoustics and clear sightlines from every seat.

The symbolic wooden ceiling consists of 11 panels that open like petals for natural ventilation. Interior decorations include red velvet, gilded woodwork, mirrors, stuccoes, and frescoes. The furnishings were designed by Vittorio Ducrot under the direction of Ernesto Basile. Notable rooms include the mahogany-and-brocade Royal Box, the Mirror Room, and the Pompeian Hall, all reflecting classical and liberty aesthetics."""@en .
```

We asked Chat to create it using the following information:

> **Subject:**  Teatro Massimo di Palermo, IRI <http://dati.beniculturali.it/iccd/schede/resource/CulturalInstituteOrSite/S012166_Teatro_Massimo>.   
> **Predicate:** `l0:description`   
> **Object:**  It features Neoclassical architecture (...) liberty aesthetics.  

---
# 8️⃣Triple for latitude and longitude

🔍We asked ChatGPT to create a triple for latitude using the **few-shot technique**, giving it an example:

![Screenshot](assets/css/Screenshot%20latlong%20prompt%20triple.png)

It generated the following triple➡️

```rdf
It generated the following triple:
@prefix geo: <http://www.w3.org/2003/01/geo/wgs84_pos#> .

<http://dati.beniculturali.it/iccd/schede/resource/CulturalInstituteOrSite/S012166_Teatro_Massimo>
    geo:lat "38.120167" .
```

We used the following information:
> **Subject:**  Teatro Massimo di Palermo, IRI <http://dati.beniculturali.it/iccd/schede/resource/CulturalInstituteOrSite/S012166_Teatro_Massimo>.   
> **Predicate:** `geo:lat`   
> **Object:**  38.120167  

Then we asked ChatGPT to do the same thing with longitude:

![Screnshot](assets/css/Screenshot%20prompt%20long%20triple.png)

Here the result➡️

```rdf
@prefix geo: <http://www.w3.org/2003/01/geo/wgs84_pos#> .

<http://dati.beniculturali.it/iccd/schede/resource/CulturalInstituteOrSite/S012166_Teatro_Massimo>
    geo:long "13.357151" .
```

We used the following information:
> **Subject:**  Teatro Massimo di Palermo, IRI <http://dati.beniculturali.it/iccd/schede/resource/CulturalInstituteOrSite/S012166_Teatro_Massimo>.   
> **Predicate:** `geo:long`   
> **Object:**   13.357151
  
Then, we asked chatGPT to merge them in one compact RDF description➡️

```rdf
@prefix geo: <http://www.w3.org/2003/01/geo/wgs84_pos#> .

<http://dati.beniculturali.it/iccd/schede/resource/CulturalInstituteOrSite/S012166_Teatro_Massimo>
    geo:lat "38.120167" ;
    geo:long "13.357151" .
```

As a final step, we manually added
1. **prefix** `arco`
2. **type** to explicitly type the resource as an **ARCO Cultural Institute or Site**.

The resulting and final triple for **latitude** and **longitude** therefore is: 

```rdf
@prefix arco: <https://w3id.org/arco/ontology/arco/> . 
@prefix geo: <http://www.w3.org/2003/01/geo/wgs84_pos#> . 
<http://dati.beniculturali.it/iccd/schede/resource/CulturalInstituteOrSite/S012166_Teatro_Massimo>
 a arco:CulturalInstituteOrSite ; 
geo:lat "38.120167" ; 
geo:long "13.357151" .
```

---
## 9️⃣RDF Triple for official image 

We noticed the predicate used for Teatro Comunale di Bologna for adding a picture was `foaf:depiction`. Chat suggested a more specific predicate for ArCo: `arco:hasRepresentative` and explained us the difference between the two: 

![Screenshot](assets/css/Screenshot%20prompt%20image.png)

➡️Therefore, we decided to use `arco:hasReprentative`as predicate. 

We used the following information: 

> **Subject:**  Teatro Massimo di Palermo, IRI <http://dati.beniculturali.it/iccd/schede/resource/CulturalInstituteOrSite/S012166_Teatro_Massimo>.   
> **Predicate:** `arco:hasRepresentative`   
> **Object:** The URL of the image hosted on Wikimedia Commons (https://commons.wikimedia.org/wiki/File:Teatro_Massimo_in_Palermo.jpg) 

As a final step, We asked ChatGPT to create a triple for the photographic representation.


Here the result➡️



_

[⬅️ Torna alla home]({{ '/' | relative_url }})
