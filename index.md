---
layout: default
title: Home
---

# <strong>Home<strong>

---
<img src="https://upload.wikimedia.org/wikipedia/commons/8/87/Il_Teatro_Massimo_di_Palermo.jpg" 
     alt="Teatro Massimo di Palermo" 
     width="900"
     style="border-radius:16px; box-shadow: 0 10px 30px rgba(0,0,0,0.15), 0 6px 12px rgba(0,0,0,0.10);">

<h2>About the Project</h2>
<p>
This project was developed within the framework of the <strong>KE4H (Knowledge Engineering for the Humanities)</strong> course at the <a href="https://www.unibo.it/">University of Bologna</a>.<br>
Our focus was the <strong>Teatro Massimo di Palermo</strong>, one of the most iconic opera houses in Italy and the largest in the country. Despite its cultural, historical, and artistic importance, we noticed that the Teatro Massimo is only partially represented in <a href="https://dati.beniculturali.it/arco/index.php"><strong>ArCo</strong></a>, the <a href="https://en.wikipedia.org/wiki/Knowledge_graph"></a>knowledge graph of Italian Cultural Heritage.
</p>

<p>
The aim of our work was to investigate how information about this landmark is modeled in ArCo, identify missing or incomplete data, and propose semantic enrichments. To achieve this, we combined <a href="https://en.wikipedia.org/wiki/SPARQL"><strong>SPARQL querying techniques</strong></a> with the use of <a href="https://en.wikipedia.org/wiki/Large_language_model"><strong>Large Language Models (LLMs)</strong></a>, which allowed us to generate <a href="https://en.wikipedia.org/wiki/Semantic_triple"><strong>RDF triples</strong></a> consistent with <a href="http://wit.istc.cnr.it/arco/lode/extract?lang=en&url=https://raw.githubusercontent.com/ICCD-MiBACT/ArCo/master/ArCo-release/ontologie/arco/arco.owl">ArCo’s ontology</a>.
</p>

<p>
Through this process, we explored how <strong>AI-assistants</strong> can improve the representation of cultural heritage in structured datasets, bridging gaps and expanding knowledge accessibility.
</p>



---

<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Key Objectives</title>
  <style>
    .objectives-list {
      list-style: none;
      padding: 0;
    }

    .objectives-list li {
      margin: 12px 0;
      font-size: 1.0em;
      display: flex;
      align-items: center;
    }

    .objectives-list .emoji {
      margin-right: 12px;
      font-size: 1.3em;
      color: #28a745; /* verde */
      transition: transform 0.3s ease, text-shadow 0.3s ease;
      cursor: pointer;
    }

    .objectives-list li:hover .emoji {
      transform: scale(1.4) rotate(20deg);
      text-shadow: 2px 2px 4px rgba(0,0,0,0.3);
    }
  </style>
</head>
<body>

  <h2>Key Objectives</h2>
  <ul class="objectives-list">
    <li><span class="emoji">✅</span> Investigate how the Teatro Massimo di Palermo is currently represented in ArCo.</li>
    <li><span class="emoji">✅</span> Identify missing pieces of information (e.g., coordinates, images).</li>
    <li><span class="emoji">✅</span> Test different prompting strategies (zero-shot, few-shot, CoT) with LLMs for RDF creation.</li>
    <li><span class="emoji">✅</span> Generate RDF triples to enrich the dataset using LLM-based assistants.</li>
    <li><span class="emoji">✅</span> Evaluate the benefits and limitations of integrating LLMs into cultural heritage knowledge engineering.</li>
  </ul>

</body>
</html>


---

<section id="tools" style="margin-top: 50px;">
  <h2>Tools</h2>
  <ul>
    <li><a href="http://wit.istc.cnr.it/arco/"><strong>ArCo</strong></a></li>
    <li><a href="https://dati.cultura.gov.it/sparql"><strong>ArCo SPARQL endpoint</strong></a></li>
    <li><a href="https://chat.openai.com/"><strong>ChatGPT</strong></a></li>
    <li><a href="https://gemini.google.com/?hl=it"><strong>Gemini</strong></a></li>
    <li><a href="https://github.com/"><strong>GitHub</strong></a></li>
  </ul>
</section>


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

<p>Students of the Master’s Degree in <a href="https://corsi.unibo.it/2cycle/LanguageSocietyCommunication">Language, Society and Communication</a> at the University of Bologna.</p>

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
    transition: transform 0.3s ease, box-shadow 0.3s ease; /* effetto hover */
    cursor: pointer;
  }

  .team-member:hover {
    transform: scale(1.05); /* ingrandimento */
    box-shadow: 0 8px 20px rgba(0,0,0,0.3); /* ombra più marcata */
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

