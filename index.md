---
layout: default
title: Home
---

# Home

<!-- Navigazione personalizzata -->
<nav style="margin-bottom: 30px;">
  
</nav>

---
<img src="https://upload.wikimedia.org/wikipedia/commons/8/87/Il_Teatro_Massimo_di_Palermo.jpg" 
     alt="Teatro Massimo di Palermo" 
     width="900">

## About the project

This project was developed within the framework of the KE4H (Knowledge Engineering for the Humanities) course at the University of Bologna.
Our focus was the Teatro Massimo di Palermo, one of the most iconic opera houses in Italy and the largest in the country. Despite its cultural, historical, and artistic importance, we noticed that the Teatro Massimo is only partially represented in ArCo, the knowledge graph of the Italian Cultural Heritage.

The aim of our work was to investigate how information about this landmark is modeled in ArCo, identify missing or incomplete data, and propose semantic enrichments. To achieve this, we combined SPARQL querying techniques with the use of Large Language Models (LLMs), which allowed us to generate RDF triples consistent with ArCo’s ontology.

Through this process, we explored how AI-assisted semantic modeling can improve the representation of cultural heritage in structured datasets, bridging gaps and expanding knowledge accessibility.


---

<!-- Font Awesome -->
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">

<style>
  .objectives-list {
    list-style: none;
    padding: 0;
  }

  .objectives-list li {
    margin: 10px 0;
    font-size: 1.1em;
    display: flex;
    align-items: center;
    opacity: 0;
    transform: translateX(-20px);
    animation: fadeIn 0.6s ease forwards;
  }

  .objectives-list li:nth-child(1) { animation-delay: 0.2s; }
  .objectives-list li:nth-child(2) { animation-delay: 0.4s; }
  .objectives-list li:nth-child(3) { animation-delay: 0.6s; }
  .objectives-list li:nth-child(4) { animation-delay: 0.8s; }
  .objectives-list li:nth-child(5) { animation-delay: 1s; }

  .objectives-list i {
    color: green;
    margin-right: 10px;
    transition: transform 0.3s ease;
  }

  .objectives-list li:hover i {
    transform: scale(1.3) rotate(10deg);
    color: #2ecc71;
  }

  @keyframes fadeIn {
    to {
      opacity: 1;
      transform: translateX(0);
    }
  }
</style>

<h2>Key Objectives</h2>
<ul class="objectives-list">
  <li><i class="fa-solid fa-circle-check"></i> Investigate how the Teatro Massimo di Palermo is currently represented in ArCo.</li>
  <li><i class="fa-solid fa-circle-check"></i> Identify missing pieces of information (e.g., coordinates, images, metadata).</li>
  <li><i class="fa-solid fa-circle-check"></i> Generate RDF triples to enrich the dataset using ontology-compliant modeling.</li>
  <li><i class="fa-solid fa-circle-check"></i> Test different prompting strategies (zero-shot, few-shot, CoT) with LLMs for RDF creation.</li>
  <li><i class="fa-solid fa-circle-check"></i> Evaluate the benefits and limitations of integrating LLMs into cultural heritage knowledge engineering.</li>
</ul>


---


<!-- Assicurati di includere Font Awesome nel tuo <head> -->
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">

<h2>Key Objectives</h2>
<ul>
  <li><i class="fa-solid fa-circle-check" style="color:green;"></i> Investigate how the Teatro Massimo di Palermo is currently represented in ArCo.</li>
  <li><i class="fa-solid fa-circle-check" style="color:green;"></i> Identify missing pieces of information (e.g., coordinates, images, metadata).</li>
  <li><i class="fa-solid fa-circle-check" style="color:green;"></i> Generate RDF triples to enrich the dataset using ontology-compliant modeling.</li>
  <li><i class="fa-solid fa-circle-check" style="color:green;"></i> Test different prompting strategies (zero-shot, few-shot, CoT) with LLMs for RDF creation.</li>
  <li><i class="fa-solid fa-circle-check" style="color:green;"></i> Evaluate the benefits and limitations of integrating LLMs into cultural heritage knowledge engineering.</li>
</ul>



---

## Our team

> Puoi continuare con i tuoi paragrafi, immagini, codice, liste ecc. come nel file originale.

Puoi ad esempio inserire:

```js
// codice JavaScript


---






