# Exercise 01 — Discussion on Chapter 1: Introduction

**Date:** 05.11.2026  
**Course:** Research Methods — Software Systems Engineering, University of Hildesheim  
**Source:** Exercise 1 slides; answers are suggested study answers based on Chapter 1 and the supplied article. The slides emphasize that most questions do not have one single correct answer; reasoning matters.

## 1. What is research? What is the inquiry cycle?

**Research** is a systematic process for creating new knowledge and improving our understanding of a subject. It aims to develop or improve theories that can explain and predict phenomena.

The **inquiry cycle**:
1. Start from the current theory / understanding.
2. Precisely define the problem and research question.
3. Design the study — choose an approach suitable for the question and constraints.
4. Execute the study.
5. Analyze the results.
6. Revise or improve the theory if the results require it.
7. Publish the results so others can understand, evaluate, reproduce, and build upon the work.

The cycle is iterative: results may confirm existing understanding, add knowledge, or challenge it.

## 2. Why do we collaborate in research?

Research is not only an individual activity. Collaboration and communication allow researchers to:
- share results and methods with others;
- critically examine and challenge claims;
- reproduce or verify results;
- combine expertise and perspectives;
- build further research on existing findings.

Research knowledge advances collectively, rather than remaining isolated with one researcher.

## 3. Why do we require research methods?

Research methods help make research systematic and trustworthy. Without appropriate methods, researchers may:
- draw false or unsupported conclusions;
- make avoidable mistakes;
- fail to document how results were obtained;
- produce results that cannot be replicated or evaluated;
- lose credibility, meaning other researchers may not trust the findings.

Methods do not guarantee correctness, but they help maximize objectivity, rigor, and the likelihood of reliable conclusions.

## 4. What is secondary research?

**Secondary research** synthesizes, analyzes, or reviews results from existing primary research rather than directly collecting new observations to answer the research question.

Examples include:
- systematic literature reviews;
- mapping studies;
- meta-analyses.

Primary research investigates a question directly (e.g., an experiment or case study). Secondary research studies and combines existing primary studies. Tertiary research synthesizes secondary research.

## 5. Are these research questions good or bad? Why?

There is no universal binary answer; judge them by clarity, scope, answerability, and whether they can guide a feasible study.

### RQ 1: “How can machine learning architectures and design patterns be classified?”
**Potentially good, but broad.** It is answerable through a classification/taxonomy study, likely involving secondary research and/or analysis of examples. It needs a defined scope (which architectures, patterns, domain, and classification criteria).

**Possible refinement:** “Which architectural patterns are reported for machine-learning systems used in [defined domain], and how can they be categorized by their main characteristics?”

### RQ 2: “What kind of practices are included in machine learning system developments?”
**Too broad / unclear as written.** “Practices” and “machine learning system developments” need definitions, and the population or context is unspecified.

**Possible refinement:** “Which engineering practices are reported in the development of production machine-learning systems, and how are they used across the development lifecycle?”

### RQ 3: “Can we transplant a software organ into a host that, after transplantation, still passes all of its regression tests?”
**Good, focused, and empirically testable**, assuming “software organ,” “host,” and transplantation are operationally defined. It asks whether a technique can achieve a measurable outcome: passing the host's regression tests after transplantation.

Potential study: perform transplantation on selected software systems and evaluate test results.

### RQ 4: “What is the computation effort to find these organs?”
**Good and measurable**, but should define the transplantation approach, systems, and what counts as computation effort (e.g., runtime, CPU time, memory, or number of candidate analyses).

It can be answered by measuring the computational cost of organ discovery across a defined set of systems.

### RQ 5: “Can automated transplantation transfer useful new functionality into the host?”
**Interesting and testable, but “useful” needs operationalization.** Define how usefulness is evaluated (e.g., functionality added, requirements fulfilled, test coverage, expert assessment, or user value) and define the systems and technique.

Possible study: evaluate whether transplanted functionality works, passes relevant tests, and satisfies specified requirements.

## 6. What is peer review? What is a peer?

**Peer review** is an evaluation of research by other researchers with relevant expertise before publication (or as part of a publication process).

A **peer** is someone who has comparable relevant expertise in the research area—not necessarily someone of the same age, institution, or status.

Reviewers assess aspects such as relevance, methodology, evidence, clarity, validity, and contribution. Peer review can improve quality and identify problems, but it does **not guarantee** that a paper is correct.

## 7. Article discussion — “Nutrition Science’s Most Preposterous Result” / ice-cream finding

### What is the central issue?
The article discusses observational research that found an unexpected association between ice-cream/dairy-dessert consumption and lower diabetes-related risk. Some researchers questioned or downplayed the finding because it seemed implausible, had limited supporting evidence, and might be explained by **reverse causation** or other biases.

### Why is this relevant to Research Methods?
- **Unexpected results:** Researchers should not dismiss results merely because they conflict with expectations or prevailing beliefs.
- **Correlation vs. causation:** An observational association does not establish that eating ice cream causes a reduction in diabetes risk.
- **Reverse causation:** People at higher risk of diabetes, or people changing their diet due to health concerns, may reduce ice-cream consumption—making the association appear protective.
- **Confounding and bias:** Other factors may influence both diet and health outcomes.
- **Uncertainty:** Small samples, limited measurements, and wide uncertainty can make results less reliable.
- **Interpretation in context:** Findings should be assessed alongside the broader literature and plausible explanations, but existing beliefs should not cause researchers to selectively ignore inconvenient evidence.
- **Replication and stronger designs:** Further studies—and potentially a randomized controlled trial, if feasible and ethical—would help assess whether the association is causal.

### Main takeaway
A surprising finding should trigger careful scrutiny, further investigation, and transparent reporting—not automatic acceptance or dismissal. Research methods help distinguish an interesting association from reliable evidence for a causal claim.

## Quick revision checklist
- [ ] Define research and explain the inquiry cycle.
- [ ] Explain why collaboration matters.
- [ ] Explain why research methods are necessary.
- [ ] Distinguish primary, secondary, and tertiary research.
- [ ] Evaluate RQs using clarity, scope, answerability, feasibility, and operational definitions.
- [ ] Define peer review and its limitations.
- [ ] Explain correlation vs. causation, reverse causation, confounding, and why surprising results require careful investigation.
