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


<h2>About the Project</h2>
<p>
This project was developed within the framework of the <strong>KE4H (Knowledge Engineering for the Humanities)</strong> course at the University of Bologna.<br>
Our focus was the <strong>Teatro Massimo di Palermo</strong>, one of the most iconic opera houses in Italy and the largest in the country. Despite its cultural, historical, and artistic importance, we noticed that the Teatro Massimo is only partially represented in <strong>ArCo</strong>, the knowledge graph of Italian Cultural Heritage.
</p>

<p>
The aim of our work was to investigate how information about this landmark is modeled in ArCo, identify missing or incomplete data, and propose semantic enrichments. To achieve this, we combined <strong>SPARQL querying techniques</strong> with the use of <strong>Large Language Models (LLMs)</strong>, which allowed us to generate <strong>RDF triples</strong> consistent with ArCo’s ontology.
</p>

<p>
Through this process, we explored how <strong>AI-assisted semantic modeling</strong> can improve the representation of cultural heritage in structured datasets, bridging gaps and expanding knowledge accessibility.
</p>



---

<style>
  .objectives-list {
    list-style: none;
    padding: 0;
  }

  .objectives-list li {
    margin: 10px 0;
    font-size: 1.0em;
    display: flex;
    align-items: center;
    opacity: 0;
    transform: translateX(-20px);
  }

  

  .objectives-list .emoji {
    margin-right: 10px;
    font-size: 1.2em;
    transition: transform 0.3s ease;
  }

  .objectives-list li:hover .emoji {
    transform: scale(1.3) rotate(10deg);
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
  <li><span class="emoji">✅</span> Investigate how the Teatro Massimo di Palermo is currently represented in ArCo.</li>
  <li><span class="emoji">✅</span> Identify missing pieces of information (e.g., coordinates, images, metadata).</li>
  <li><span class="emoji">✅</span> Generate RDF triples to enrich the dataset using ontology-compliant modeling.</li>
  <li><span class="emoji">✅</span> Test different prompting strategies (zero-shot, few-shot, CoT) with LLMs for RDF creation.</li>
  <li><span class="emoji">✅</span> Evaluate the benefits and limitations of integrating LLMs into cultural heritage knowledge engineering.</li>
</ul>




---


<h2>Our Team</h2>
<p>This project was collaboratively developed by:</p>

<div class="team-container">
  <div class="team-member">
    <span class="emoji">👩🏻</span>
    <span class="name">Macheda Ilaria</span>
  </div>
  <div class="team-member">
    <span class="emoji">👩🏻</span>
    <span class="name">Sinopoli Sendy</span>
  </div>
  <div class="team-member">
    <span class="emoji">👩🏻</span>
    <span class="name">Tsingos Matilde</span>
  </div>
</div>

<p>Students of the Master’s Degree in Language, Society and Communication at the University of Bologna.</p>

<style>
  .team-container {
    display: flex;
    gap: 1em; /* spazio tra le card */
    flex-wrap: wrap; /* si adattano se lo schermo è piccolo */
  }

  .team-member {
    background-color: #e0f7e9; /* sfondo leggero verde */
    padding: 1em;
    border-radius: 10px;
    text-align: center;
    width: 150px;
    box-shadow: 0 2px 5px rgba(0,0,0,0.1);
    font-family: Arial, sans-serif;
  }

  .emoji {
    font-size: 2em;
    display: block;
    margin-bottom: 0.5em;
  }

  .name {
    font-weight: bold;
    font-size: 1em;
    display: block;
  }
</style>


---






