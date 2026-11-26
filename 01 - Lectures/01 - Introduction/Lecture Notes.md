# Lecture 01 — Research Methods: Introduction

**Lecturer:** Prof. Dr. Klaus Schmid  
**Software Systems Engineering, University of Hildesheim**  
**Lecture date shown on slides:** 20 April 2020

> Primary-source basis: Chapter 1 slides and transcript. These notes organize the lecture content and add examples only where explicitly labelled.

## 1. Motivation: Why research methods?
Research methods are necessary to conduct proper research. Without systematic approaches:
- We may reach **false conclusions**.
- Other researchers may not be able to **repeat** our work.
- Our findings may not be **believable**, because readers cannot understand how the results were obtained or assess their reliability.

Research is collaborative knowledge-building. Findings need to be understandable and reproducible so others can build upon them. Research capability is required throughout university work, including study projects and the Master's thesis, and is also relevant in industry.

## 2. What is research?
Research is a **systematic approach to creating new knowledge**.
- **New:** knowledge not previously known (in the lecture's sense, new to the world).
- **Knowledge:** results have a sufficiently strong foundation to be believable, rather than being unsupported assumptions or ideas.

The typical ultimate goal is **theory formation**: developing an understanding that enables predictions about situations or outcomes that have not yet been observed or built.

### Theory–experiment interaction
1. Theory predicts an outcome.
2. An experiment or observation is performed.
3. The real outcome is compared with the prediction.
4. The outcome may support the theory or differ from it.
5. Unexpected results can inform and improve theory.

This feedback loop is fundamental to research in many disciplines.

## 3. The Inquiry Cycle
The lecture's cycle consists of:

1. **Precisely define the problem** — formulate the research question.
2. **Design the research study** — decide how to answer the question.
3. **Execute the study** — carry out the planned procedure.
4. **Analyze results** — interpret what was observed or measured.
5. **Revise theory (if necessary)** — update understanding based on results.
6. **Publish research results** — communicate the work so others can assess and build on it.

The research question is often refined iteratively. A poorly defined question makes it difficult to select a study design and conduct meaningful research.

## 4. What is a theory?
A theory is a **combination of statements and derivation rules** that allows us to predict outcomes.

Two purposes:
- **Explanation:** understanding why/how a phenomenon occurs (typical focus in natural sciences).
- **Construction:** using knowledge to create something with desired properties (typical focus in engineering).

### Mathematics
Mathematics is a special case: it primarily reasons **within a theory**, using derivation rules to establish consequences. It does not necessarily investigate specific real-world objects directly.

### Example: a stone falling
- **Physics:** explains why the stone falls and predicts its motion using physical laws.
- **Mathematics:** derives consequences from the physical theory.
- **Engineering:** constructs an apparatus that makes a stone travel a desired distance.

The central artefact is the theory describing motion, but disciplines approach it with different goals.

## 5. Research in Computer Science and Information Systems
It depends on the research goal. CS/IS research may be explanatory or engineering-oriented.

**Explanatory / natural-science-like examples:**
- Understanding how software is created in real development teams.
- Understanding how introducing an IT solution transforms an organization.

**Engineering examples:**
- Creating a new approach for more efficient software testing.
- Developing methods for introducing IT solutions successfully in organizations.

Engineering artefacts may be **methods**, **tools**, or complete **software solutions**.

## 6. Research questions
A valid research question, according to the lecture, should:
- **Support prediction**, and
- **Be answerable at least in principle**.

Examples of valid questions:
- Does the Moon revolve around Earth, and why?
- What kinds of errors can testing method X identify?
- How does testing compare with inspections for finding software defects?
- Is there a sorting algorithm more performant than one with a particular complexity?

A problematic question: **“What is the best development method?”** It is too unbounded: it is not clear how to enumerate all possible methods or predict all their outcomes. A more answerable formulation limits the comparison to a defined set and criteria.

## 7. Study design
Study design answers: **How will we approach generating knowledge and answering the research question?**

The choice depends on:
- The **type of research question**.
- **Context factors / feasibility** — what can realistically be done.
- The **required qualities of the results**, including threats to validity and how transferable the knowledge should be.

There are multiple approaches, each with potential traps and guidelines for avoiding them.

### Characteristics of good research
- **Well-documented:** procedures and decisions are clearly described.
- **Replicable:** others can repeat the research.
- **Refutable:** others can identify problems and challenge claims if evidence or reasoning is flawed.

## 8. Publications and peer review
High-level publication venues:
- **Workshop:** often preliminary work and discussion; exchange ideas and receive feedback.
- **Conference:** validated work, typically with a page limit.
- **Journal:** larger and more detailed work, often extensive.

The relative prestige of conferences and journals differs by discipline. Computer Science often places substantial value on conferences.

### Peer review
Knowledgeable peers evaluate submitted work, identify flaws, and provide feedback. It is a major quality mechanism, but **not a guarantee of correctness**:
- Reviewers may miss issues.
- Reviewer feedback can influence the paper (ideally positively).
- Closed communities can undermine the process.

## 9. Types / layers of research

### Primary, secondary, tertiary
- **Primary research:** directly investigates/evaluates a research question.
- **Secondary research:** synthesizes primary studies to create a broader picture of the state of research.
- **Tertiary research:** synthesizes secondary studies; relatively rare.

### Empirical vs. non-empirical
- **Empirical:** draws on reality through observation, data collection, or investigation (possibly controlled); can study people, organizations, or technical artefacts.
- **Non-empirical:** theoretical work, including mathematical reasoning.

Neither is inherently “better”; both have a legitimate role.

## 10. Method-selection dimensions
Research methods address different needs and can vary along dimensions such as:
- **Empirical ↔ formal**
- **Technology-oriented ↔ people-oriented**

Select a method based on:
1. **Research question:** concerns people (developers/users), technical artefacts, or consequences of a theory?
2. **Replication scale:** how many observations or replications are feasible? Human studies may have limited participants/projects; technical artefacts may allow very large numbers.
3. **Research purpose:** develop concepts and hypotheses, validate a hypothesis, or map the state/frontier of research?

## 11. Course roadmap
The lecture introduces the course toolbox:
- **Fundamental concepts:** metrics, statistics, threats to validity.
- **Primary methods:** human experiments, case studies, technical experiments, formal methods.
- **Secondary methods:** systematic literature reviews, mapping studies.
- **Auxiliary method:** grounded theory.

## 12. Final takeaway
Scientific research does not guarantee absolute correctness. Observations, reasoning, or study execution can contain errors. Nevertheless, a systematic, transparent, and appropriate methodology is the best way to produce credible knowledge that can be examined and built upon.

---
## Source files
- Chapter 1 slides: `Attachments/Slides/RM-ch1-Intro.pdf`
- Chapter 1 transcript: `Attachments/Transcripts/RM-ch1-Intro-transcript.pdf`
- [[Summary]]
- [[Key Concepts]]
- [[Questions]]
