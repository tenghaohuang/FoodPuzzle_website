---
layout: project_page
permalink: /

title: "FOODPUZZLE: Developing Large Language Model Agents as Flavor Scientists"
authors:
  - "Tenghao Huang¹"
  - "Donghee Lee²*"
  - "John Sweeney*"
  - "Jiatong Shi"
  - "Emily Steliotes²"
  - "Matthew Lange²"
  - "Jonathan May¹"
  - "Muhao Chen²"
affiliations:
  - "¹University of Southern California"
  - "²University of California, Davis"
paper: "https://arxiv.org/abs/2409.12832"
code: "https://github.com/tenghaohuang/FoodPuzzle"
data: "https://github.com/tenghaohuang/FoodPuzzle"
---

<!-- Using HTML to center the abstract section -->
<div class="columns is-centered has-text-centered">
  <div class="column is-four-fifths">
    <h2>Abstract</h2>
    <div class="content has-text-justified">
      Flavor development in the food industry is increasingly challenged by the need for rapid
      innovation and precise flavor profile creation.
      Traditional flavor research methods typically
      rely on iterative, subjective testing, which lacks
      the efficiency and scalability required for modern demands. This paper presents three contributions to address the challenges. Firstly,
      we define a new problem domain for scientific agents in flavor science, conceptualized
      as the generation of hypotheses for flavor profile sourcing and understanding. To facilitate research in this area, we introduce the
      FOODPUZZLE, a challenging benchmark consisting of 978 food items and 1,766 flavor
      molecules profiles. We propose a novel Scientific Agent approach, integrating in-context
      learning and retrieval augmented techniques to
      generate grounded hypotheses in the domain
      of food science. Experimental results indicate
      that our model significantly surpasses traditional methods in flavor profile prediction tasks,
      demonstrating its potential to transform flavor
      development practices.
    </div>
  </div>
</div>

<hr />

<h2>Introduction</h2>
<p>
  The burgeoning demand for novel and appealing
  flavors in the food industry necessitates expedited
  innovation cycles without compromising on quality
  (Hofmann et al., 2018). Traditionally, the process
  of ingredient sourcing and evaluation for flavor
  development has been reliant on manual assessment
  and human expertise. In addition to being labor-
  intensive and subjective, this process also relies
  on time-consuming iterations, hindering the pace
  of flavor development (Engeseth and Ac Pangan,
  2018; Hofmann et al., 2018; Patel and Patel, 2019).
  Additionally, complex flavor interactions, together
  with the vast array of available ingredients, present
  formidable challenges for food scientists in optimizing flavor profiles (Hamilton and Lahne, 2020).
</p>
<p>
  Recent advancements in Large Language Models (LLMs) have revolutionized traditional scientific
  methodologies across a broad spectrum of
  disciplines. In fields ranging from biology and
  chemistry to physics and material sciences, researchers
  have employed LLM technologies to analyze complex
  datasets, uncover hidden patterns, and narrow down
  the search spaces of scientific problems (Horawalavithana
  et al., 2022; Singhal et al., 2022; O’Donoghue et al.,
  2023; Song et al., 2023; Hong et al., 2024). This trend
  highlights the transformative potential of LLMs
  in reshaping traditional paradigms and catalyzing
  breakthroughs.
  This paper explores how the integration of LLMs
  can streamline and enhance the process of evaluating
  ingredient sources for their flavor-giving potential.
  However, the application of LLMs in ingredient
  sourcing and flavor formulation is hindered by
  a significant barrier: the absence of high-quality,
  domain-specific datasets.
</p>

<h2>Objective</h2>
<ol>
  <li><strong>Define Flavor Profile Sourcing</strong> as a novel LLM agent problem in flavor science.</li>
  <li><strong>Introduce FOODPUZZLE</strong>, a benchmark of 978 food items and 1,766 flavor molecules.</li>
  <li><strong>Develop a Scientific Agent</strong> integrating in-context learning & retrieval-augmented techniques.</li>
</ol>

<h2>Key Ideas</h2>
<ul>
    <li><strong>Scientific Agent</strong>: Combines in-context learning and retrieval from scholarly articles to provide evidence-based reasoning.</li>
</ul>

<p style="text-align:center;">
  <img src="/static/image/pipeline.jpg" alt="" style="max-width: 60%;"/>
</p>
<p style="text-align:center;"><em>Figure 1: An overview of the Scientific Agent pipeline.</em></p>

---

<h2>Dataset: FOODPUZZLE</h2>
<ul>
  <li>
    <strong>Source</strong>: Built upon <em>FlavorDB</em> (Garg et al., 2018).
  </li>
  <li>
    <strong>Scope</strong>: 978 foods mapped to 1,766 flavor molecules, allowing complex, realistic flavor prediction tasks.
  </li>
<p style="text-align:center;">
  <img src="/static/image/fs_categorization.jpg" alt="" style="max-width: 60%;"/>
</p>
<p style="text-align:center;"><em>Figure 2: Example of food and flavor molecule connections in FOODPUZZLE.</em></p>

  <li>
    <strong>Tasks</strong>:
    <ol>
      <li>
        <strong>Molecular Food Prediction (MFP)</strong>: Predict the food or food category from flavor molecules.
      </li>
      <li>
        <strong>Molecular Profile Completion (MPC)</strong>: Identify missing molecules in a partially known flavor profile of a target food.
        <pre>
### Sample MPC task:)
{
  "id": 0,
  "task": "MPC",
  "known_molecules": [
    "L-arginine",
    "3-Methylindole",
    "2,5-Dimethylpyrazine",
    "4-Methyl-2-pentanone",
    "2-Methylbutyraldehyde",
    "Styrene",
    "Methyl butyrate",
    "1-Octen-3-Ol",
    "3-(Methylthio)propionaldehyde",
    "..."
  ],
  "target_food": "Egg",
  "missing_molecules": [
    "Diethyl sulfide",
    "lactic acid",
    "2-Pentylfuran",
    "..."
  ]
}
        </pre>
      </li>
    </ol>
  </li>
</ul>

---



<h2>Significance</h2>
<ol>
  <li><strong>Efficient Flavor Innovation</strong>: Streamlines flavor molecule identification.</li>
  <li><strong>Grounded Hypotheses</strong>: Enhances reliability with retrieval-augmented, evidence-based outputs.</li>
  <li><strong>Broad Applicability</strong>: Demonstrates how advanced AI can tackle other specialized scientific tasks.</li>
</ol>

<h2>Table: Comparison of Approaches</h2>
<table style="width:100%; border-collapse: collapse; text-align: left;">
  <thead>
    <tr style="border-bottom: 2px solid #ccc;">
      <th style="padding: 8px;">Approach</th>
      <th style="padding: 8px;">Knowledge Source</th>
      <th style="padding: 8px;">Learning Method</th>
      <th style="padding: 8px;">Application Area</th>
    </tr>
  </thead>
  <tbody>
    <tr style="border-bottom: 1px solid #ccc;">
      <td style="padding: 8px;">Domain-Specific LLMs</td>
      <td style="padding: 8px;">Specialized corpora</td>
      <td style="padding: 8px;">Fine-tuning</td>
      <td style="padding: 8px;">Often limited in generalizability</td>
    </tr>
    <tr style="border-bottom: 1px solid #ccc;">
      <td style="padding: 8px;">Zero-Shot Foundation Models</td>
      <td style="padding: 8px;">Large generic corpora</td>
      <td style="padding: 8px;">Prompt-based</td>
      <td style="padding: 8px;">High generality, may lack domain detail</td>
    </tr>
    <tr style="border-bottom: 1px solid #ccc;">
      <td style="padding: 8px;">In-Context Retrieval</td>
      <td style="padding: 8px;">+ Past training examples (BM25, dense index)</td>
      <td style="padding: 8px;">Prompt-level retrieval</td>
      <td style="padding: 8px;">Balances domain knowledge with generative flexibility</td>
    </tr>
    <tr>
      <td style="padding: 8px;"><strong>Scientific Agent</strong></td>
      <td style="padding: 8px;">+ Scholarly articles + FOODPUZZLE demos</td>
      <td style="padding: 8px;">In-context + RAG + CoT</td>
      <td style="padding: 8px;">Combines domain coverage with evidence-based reasoning</td>
    </tr>
  </tbody>
</table>

<h2>Conclusion</h2>
<p>
  Our study highlights the transformative potential of LLM agents in flavor science. By defining
  flavor profile sourcing and understanding as an LLM-agent task, introducing the FOODPUZZLE
  dataset, and designing a retrieval-augmented scientific agent, we demonstrate not only improved
  predictive performances but also transparent and
  substantiated results. This sets a strong precedent
  for further AI-driven explorations in complex scientific domains beyond flavor science.
</p>

<h2>Citation</h2>
<pre>
@misc{huang2024foodpuzzle,
  title  = {FOODPUZZLE: Developing Large Language Model Agents as Flavor Scientists},
  author = {Huang, Tenghao and Lee, Donghee and Sweeney, John and Shi, Jiatong 
            and Steliotes, Emily and Lange, Matthew and May, Jonathan and Chen, Muhao},
  howpublished = {arXiv preprint arXiv:2409.12832v3},
  year   = {2024}
}
</pre>
