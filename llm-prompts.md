---
layout: default
title: LLM Prompts
---

# <strong>LLM Prompts<strong>


---

In this section, we explore the use of **Large Language Models (LLMs)**, specifically **ChatGPT** and **Google Gemini**, to support the process of enriching the ArCo Knowledge Graph with new cultural heritage data.

Presented below are the three prompting techniques we used to interrogate AI: ⬇️

```rdf
📌 ZERO-SHOT PROMPTING TECHNIQUE                      

•No examples needed

•Flexible use

•Saves time

•Generalizes knowledge

•Direct interaction

•Quick testing


📌 FEW-SHOT PROMPTING TECHNIQUE

• Provides examples – Shows the AI a few examples of the desired input-output behavior.

• Improves accuracy – Helps the AI understand the task better than zero-shot prompting.

• Guides style and format – Ensures outputs follow a specific tone or structure.

• Reduces ambiguity – Clarifies what the user expects from the AI.

• Flexible learning – Works even without full model retraining.

• Good for complex tasks – Useful when tasks are too nuanced for zero-shot prompts.


📌 CHAIN-OF-THOUGHT PROMPTING TECHNIQUE

• Step-by-step reasoning – Encourages the AI to break down problems into intermediate steps before giving a final answer.

• Improves complex problem solving – Useful for math, logic, or multi-step reasoning tasks.

• Reduces errors – Makes the AI less likely to jump to an incorrect conclusion.

• Transparent thinking – Shows the reasoning process, not just the answer.

• Better accuracy – Often leads to more precise and reliable outputs.

• Supports learning and debugging – Helps users understand how the AI reached its conclusion.
```


## 1️⃣  Missing information: the full official name


Using a **zero-shot technique**, we prompted ChatGPT and Gemini to retrieve information regarding the full official name of the Teatro Massimo in Palermo, without offering any example.


### [ChatGPT](https://chat.openai.com/)


<img width="602" height="303" alt="image" src="https://github.com/user-attachments/assets/bdf58daf-0813-41ba-b2b1-c5ef62ffd808" />


### [Gemini](https://gemini.google.com/)


<img width="602" height="169" alt="image" src="https://github.com/user-attachments/assets/155e8df5-a588-4ccc-9af1-c8080f49f2bb" />

✅ **LLMS comparison**:

ChatGPT gave us a more precise answer, but both provided the information that we were looking for. 


## 2️⃣ Missing information: the architects' names

Using a **zero-shot technique**, we prompted ChatGPT to retrieve information about the architects who designed the Teatro Massimo di Palermo.

### [ChatGPT](https://chat.openai.com/)

<img width="602" height="353" alt="image" src="https://github.com/user-attachments/assets/f6e2b546-86ec-42dd-96d4-6d2d3b48d2b5" />
<img width="602" height="117" alt="image" src="https://github.com/user-attachments/assets/1373bb54-c479-4292-ac21-2b13dd33cd3c" />

### [Gemini](https://gemini.google.com/)

<img width="602" height="240" alt="image" src="https://github.com/user-attachments/assets/c822882a-d1bd-42cf-931d-8c08be0fe85c" />

✅ **LLMS comparison**: 

Both ChatGPT and Gemini provided accurate and reliable information, including the names of the two architects who designed the Teatro Massimo di Palermo, as well as two key dates: the start of construction and the inauguration date.



## 3️⃣ Missing information: cultural events hosted by Teatro Massimo

The prompt we wrote uses a **few-shot technique** by providing Chat GPT and Gemini with examples of other cultural institutions and the types of events they host. By showing these examples, the AI can better understand the expected answer format and the scope of information desired. The prompt clearly asks for a detailed and comprehensive list of events at the Teatro Massimo, including operas, concerts, ballet, and festivals, allowing the model to generate a structured and relevant response.


### [ChatGPT](https://chat.openai.com/)

<img width="501" height="411" alt="image" src="https://github.com/user-attachments/assets/4789fd65-16b9-4411-918f-16054fcba49c" />
<img width="455" height="308" alt="image" src="https://github.com/user-attachments/assets/f381198b-0b90-40e1-99cb-cb3482ac491c" />
<img width="450" height="289" alt="image" src="https://github.com/user-attachments/assets/ab0bbfba-efc1-4ead-9f98-c6720a748c57" />
<img width="454" height="326" alt="image" src="https://github.com/user-attachments/assets/c0703584-70d9-4df7-b4a4-a6be7ef89a37" />
<img width="488" height="189" alt="image" src="https://github.com/user-attachments/assets/62a5a8d2-c368-47a0-811a-895fd86fa25c" />

### [Gemini](https://gemini.google.com/)

<img width="602" height="629" alt="image" src="https://github.com/user-attachments/assets/2d3b9e97-301c-453e-ad01-00467a5deeeb" />
<img width="602" height="458" alt="image" src="https://github.com/user-attachments/assets/ab9341d3-4ecc-4c21-9af2-1d4d9a762cc7" />


✅ **LLMS comparison**: 

➡️ Both provided right answers, but:

-**ChatGPT**: Focuses on specific events and examples, mentioning exact opera productions with dates, notable premieres, and concrete instances of ballet and concerts.


-**Gemini**: Adopts a broader approach, categorizing the theater’s offerings—opera, ballet, concerts, educational programs, and festivals—without dates, highlighting repertoire variety, youth initiatives, and special activities like guided tours and immersive productions.


-**ChatGPT**: Emphasizes performing arts activities, including conferences and workshops.


-**Gemini**: Highlights the theater’s wider cultural role, including fundraising events, tours, and other theatrical productions.



## 4️⃣ Missing information: restoration and intervention

Using a **Chain-of-Thought** technique, the question we wrote asks for a step-by-step account of the restoration and interventions at Teatro Massimo. It focuses on understanding when and why restorations occurred, the problems or challenges faced during the work, and the results or impact on the theater. The goal is to get a complete picture of the theater’s restoration history in a logical, chronological order.

### [ChatGPT](https://chat.openai.com/)

<img width="602" height="653" alt="image" src="https://github.com/user-attachments/assets/916b4c12-574d-4ca9-bfb7-0f2446403817" />
<img width="602" height="717" alt="image" src="https://github.com/user-attachments/assets/cddefc9e-f4c2-4178-b519-abc3434d2bb6" />

### [Gemini](https://gemini.google.com/)

<img width="602" height="621" alt="image" src="https://github.com/user-attachments/assets/1d0bdd97-33c7-41e4-8c44-c8fb2053ed6a" />
<img width="602" height="549" alt="image" src="https://github.com/user-attachments/assets/e477746e-744d-4e82-989f-3c4c5626d771" />

✅ **LLMS comparison**:

➡️ Cheching on Wikipedia, we noticed that both provided right answers, but:


-**ChatGPT**: Adds an image; presents a chronological and technical structure (it follows the timeline from construction, decline, restoration, to reopening)
emphasizing structural issues, bureaucracy, and modernization. It is more complete and historically constructed compared to Gemini. It follows more faithfully the structure given by the Chain-of-thought prompt. It includes details such as names and specific interventions. 

-**Gemini**: Uses a thematic and narrative structure, organizing information around social, cultural, and political context.
Emphasizes symbolic and civic aspects, like the fight against the Mafia and the city’s cultural revival.
Does not strictly follow a chronological sequence, prioritizing a storytelling approach with cultural meaning.

-**ChatGPT**: Focuses on architectural and acoustic preservation.


-**Gemini**: Frames the reopening as a civic triumph and connects it to popular culture.


Overall ⬇️: 

**ChatGPT**→ its approach is historical and factual.

**Gemini**→ it is narrative and culturally rich.


## 5️⃣ Missing information: type of architecture

Using a **few-shot prompting technique**, we asked both ChatGPT and Gemini which would be the best description under the property **`dc:type`**, considering the example of Teatro comunale di Bologna.

### [ChatGPT](https://chat.openai.com/)

<img width="602" height="440" alt="image" src="https://github.com/user-attachments/assets/a824ef8c-f9a2-435e-8bfd-bd95446e48fa" />

### [Gemini](https://gemini.google.com/)

<img width="602" height="404" alt="image" src="https://github.com/user-attachments/assets/6c5e5d16-9331-4727-ab05-160f8c95953b" />

✅ **LLMS comparison**:

Considering both answers, we thought the best description to add was “architettura civile”. 


## 6️⃣ Missing information: wikidata link

We asked both ChatGPT and Gemini whether a Wikidata page about Teatro Massimo di Palermo existed, using a **zero-shot prompting technique** .

### [ChatGPT](https://chat.openai.com/)

<img width="514" height="372" alt="image" src="https://github.com/user-attachments/assets/0a77cbf7-5bff-484b-812e-76cafae012e2" />

### [Gemini](https://gemini.google.com/)

<img width="576" height="436" alt="image" src="https://github.com/user-attachments/assets/7bf13c12-e657-4bd9-afc3-8d74d36d706e" />

✅ **LLMS comparison**:

They both provided the correct ID for Teatro Massimo.

## 7️⃣ Missing information: architectural description


We decided to write under the property **`l0:description`** some architectural information; we first started by asking both ChatGpt and Gemini some architectural information about Teatro Massimo di Palermo, using a **zero-shot prompting technique**: 

### [ChatGPT](https://chat.openai.com/)

<img width="602" height="601" alt="image" src="https://github.com/user-attachments/assets/c5caf7e3-deca-4d32-9569-e3f8409b69bf" />
<img width="602" height="603" alt="image" src="https://github.com/user-attachments/assets/fb9513af-bd0b-40d8-8e0c-ee3f0c450063" />

### [Gemini](https://gemini.google.com/)

<img width="602" height="417" alt="image" src="https://github.com/user-attachments/assets/8b22d416-28ab-4d98-9471-c103c8084c35" />
<img width="602" height="287" alt="image" src="https://github.com/user-attachments/assets/f10eb756-1b20-447f-ba2e-6b9598b63e3c" />

✅ **LLMS comparison**:

-**Gemini**: More text-heavy, with fluid prose and a narrative format. It separates into Exterior, Interior, and History & Significance, but the structure is less modular. Formatting is standard (bold/italics only) and it emphasizes historical background more.

-**ChatGPT**: Well-structured with clear sections, headings, emojis, and bullet points — very skimmable. Breaks content into more modules (Exterior, Dome, Auditorium, Ceiling, Interior Decoration). Rich formatting (bold, italics, icons) highlights key ideas and details.

-**Gemini**: Accurate but higher-level, focusing on providing context and storytelling. Works better for academic or essay-style explanations without visual frills.

-**ChatGPT**: Very accurate and detailed, often including precise data (e.g., dome diameter, materials). Covers more subtopics such as acoustics, restoration, mechanical ceiling, and decorative elements.

Overall ⬇️:

-**Gemini** → Narrative, context-driven, formal tone; stronger for historical explanations and structured essays.

-**ChatGPT** → Modular, visually engaging, detailed, and skimmable; stronger for presentations, quick reading, and broader coverage.


Another thing we asked ChatGPT was the difference between arco:hasDescription and l0:description, to understand which property would be more suitable for inserting various architectural information in text form. We asked ChatGPT, which would be the best option, using a **chain-of-thought technique**:

<img width="602" height="544" alt="image" src="https://github.com/user-attachments/assets/3426f095-07b4-476d-9755-9224b9e1935b" />
<img width="560" height="454" alt="image" src="https://github.com/user-attachments/assets/aebfcd9f-0403-4cbf-8e88-3069aa60d9d1" />

In conclusion, we opted for l0:description because we thought it was the most appropriate choice given the kind of description we wanted to add. 

## 8️⃣ Missing information: latitude and longitude

We asked both ChatGPT and Gemini for information about the latitude and longitude of the Teatro Massimo di Palermo, using a **zero-shot prompting technique**:

### [ChatGPT](https://chat.openai.com/)

<img width="602" height="263" alt="image" src="https://github.com/user-attachments/assets/7637d69d-96d2-40a2-b0ae-f880102444de" />

### [Gemini](https://gemini.google.com/)

<img width="602" height="240" alt="image" src="https://github.com/user-attachments/assets/bb73b291-5eda-4a87-862a-468bb479972a" />

✅ **LLMS comparison**:

They both gave the exact same answer, but Chat GPT was more precise giving also the sources from which it gathered information (<a href="https://www.outdooractive.com/en/">Outdooractive</a> and <a href="https://mapcarta.com/">Mapcarta</a>).

## 9️⃣ Missing information: official image

We asked both ChatGPT and Gemini for the URL of a picture of the Teatro di Palermo using the few-shot prompting technique, giving it an example. 

### [ChatGPT](https://chat.openai.com/)

<img width="558" height="358" alt="image" src="https://github.com/user-attachments/assets/792ece84-6aea-4414-8307-9e1d73b66d50" />
<img width="602" height="375" alt="image" src="https://github.com/user-attachments/assets/ef3af9a4-3360-42d3-8d5a-78b7ee68f592" />

### [Gemini](https://gemini.google.com/)

<img width="602" height="323" alt="image" src="https://github.com/user-attachments/assets/2a3c3b23-cec6-4174-a14d-ca76d76dee18" />

✅ **LLMS comparison**:

Checking the information reported by both the LLMs we noticed that while ChatGPT was accurate, Gemini presented a discrepancy. In fact, the Author stated by Gemini (Iacopo Nuti) did not correspond to the Autor written in Wikidata (Vitoparisi92): 

<img width="226" height="76" alt="image" src="https://github.com/user-attachments/assets/30531dba-9124-4852-8529-ed46114823fa" />


[⬅️ Torna alla home]({{ '/' | relative_url }})




























