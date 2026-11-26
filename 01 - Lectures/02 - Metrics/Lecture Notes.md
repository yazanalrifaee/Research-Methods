# Lecture 02 — Metrics

**Lecturer:** Prof. Dr. Klaus Schmid / Dr. Holger Eichelberger  
**Course:** Research Methods — Software Systems Engineering  
**Lecture date:** 28 April 2020

## Overview
Chapter 2 focuses on acquiring data that is meaningful and usable in the scientific process. Metrics help characterize the object of study and make observations measurable, interpretable, and comparable. The chapter covers:
1. Fundamentals of metrics
2. Scale types
3. Goal-Question-Metric (GQM)
4. GQM example
5. Literature / further reading

## 1. Why metrics matter
When observing or analyzing real outcomes, researchers need to decide:
- **What** should be observed?
- **How** will the outcome be determined (measurement procedure)?
- **How** can it be quantified, and what scale is appropriate?

Without an agreed definition and procedure, two people observing the same phenomenon may reach different conclusions. Measurement is not automatically straightforward. For example, counting Lines of Code (LoC) raises questions: Are blank lines counted? Comments? Multiple statements on one line? Different conventions create different LoC metrics.

Metrics support research and practical improvement by providing evidence to characterize a situation, understand it, or evaluate change.

## 2. Measurement and metrics
A measurement maps an empirical property/attribute of an entity to a value according to a defined procedure. The procedure and interpretation matter: the value is meaningful only if it represents the intended property.

A **metric** is a defined quantitative characterization used to measure or describe an attribute. Metrics should be chosen based on the purpose and context rather than collected indiscriminately.

### Metric categories
- **Objective vs. subjective**
  - Objective: determination does not depend on the person making the measurement (or is designed to minimize such dependence).
  - Subjective: determination depends on human judgement.
- **Direct vs. indirect**
  - Direct: determined directly from an observation/measurement.
  - Indirect: calculated or derived from direct metrics. Example: productivity = size / effort.
- **Product metrics:** characterize the product/artefact (e.g., size, complexity, defects).
- **Process metrics:** characterize activities/processes (e.g., effort, duration).
- **People metrics:** characterize people-related aspects, where appropriate.

The categories are not mutually exclusive in all cases; a metric can be classified along multiple dimensions.

## 3. Scale types
The lecture distinguishes four scales. As we move from nominal to ordinal, interval, and ratio, more comparisons and operations become meaningful. The scale type constrains which statistical operations are valid.

### Nominal
- **Definition:** a set of categories/values.
- **Meaningful operation:** equality/inequality (same category or different).
- **Example:** defect classes (interface defect, control-flow defect, etc.).
- Not meaningful: greater/less, arithmetic, subtraction, or averaging category labels.

### Ordinal
- **Definition:** an ordered set of values/categories.
- **Meaningful operations:** equality and order (>, <).
- **Example:** complexity classified as low, medium, high, very high.
- Numeric labels do not make the scale interval or ratio. Coding low=1, medium=2, high=3 does not justify subtracting or averaging because distances between categories are not known to be equal.

### Interval
- **Definition:** ordered values with meaningful, constant differences (equal intervals).
- **Meaningful operations:** equality, ordering, differences; common summary/analysis operations include mean, standard deviation, correlation, regression and linear transformations.
- **Example:** Celsius temperature. The difference between 1°C and 2°C has the same meaning as between 30°C and 31°C.
- **No true zero:** zero is a point on the scale, not the absence of the measured property. Ratios such as “20°C is twice as hot as 10°C” are not meaningful.

### Ratio (called “rational” in some lecture wording)
- **Definition:** an interval scale with a meaningful absolute zero.
- **Meaningful operations:** interval-scale operations plus ratios; multiplicative comparisons are meaningful.
- **Examples:** duration, effort, mass, length, counts (when the construct and measurement procedure support this).
- “Twice as much” is meaningful because zero indicates absence of the quantity.

### Scale hierarchy
Nominal → Ordinal → Interval → Ratio. Higher levels include the operations supported by lower levels, plus additional operations.

## 4. Likert scales: caution
Likert-style questionnaire responses (e.g., strongly disagree, disagree, neutral, agree, strongly agree) are **ordinal** by strict interpretation. They are sometimes treated approximately as interval if the categories are calibrated to represent equal spacing, but equal distances are not guaranteed. The lecturer emphasizes caution.

Odd-numbered scales often include a neutral point; even-numbered scales may force respondents toward one side. Assigning numbers or drawing equally spaced lines does not prove the responses are interval measurements.

## 5. Goal-Question-Metric (GQM)
GQM is a systematic, **top-down refinement** method for identifying metrics. It was initially developed for software engineering improvement, but its approach is broadly applicable.

### Why GQM?
Metric catalogues may list many measures, but collecting large amounts of context-independent data can be costly and difficult to interpret. Metrics are **context-specific**. The goal is not to collect as many metrics as possible; it is to identify the small set of relevant measures that can answer the questions and support the goal.

### GQM structure
**Goal → Questions → Metrics**
1. Identify a high-level goal.
2. Derive questions that clarify what must be understood to achieve/assess the goal.
3. Derive metrics that can answer those questions.

**Top-down:** refine goal into questions and metrics.  
**Bottom-up interpretation:** collected metric data answers questions; the answers inform goal attainment.

A metric may serve multiple questions, and a question may require several metrics.

## 6. GQM phases
The lecture presents four phases:
1. **Planning:** prepare the measurement project and ensure participants understand its purpose and expectations.
2. **Definition:** specify the goal, questions, and metrics (the GQM plan).
3. **Data collection:** gather the data specified by the metrics.
4. **Interpretation:** interpret measurements to answer questions and assess goal attainment.

The definition phase determines what data is relevant. Data not connected to the GQM plan is generally not required for the measurement purpose.

## 7. Goal template
A GQM goal characterizes:
- **Object of study:** process, product, resource, etc.
- **Purpose:** characterize, understand, improve, evaluate, etc.
- **Quality focus:** reliability, flexibility, maintainability, effort, effectiveness, etc.
- **Viewpoint:** developer, tester, manager, customer, etc.
- **Context/environment:** company, department, project, classroom, etc.

Template:

> Analyze **[object]** for the purpose of **[purpose]**, with respect to **[quality focus]**, from the point of view of **[viewpoint]**, in the context of **[environment]**.

Changing any element can change the questions and metrics needed. This is why context-independent metric definitions are often ineffective.

## 8. GQM planning / abstraction sheet
The abstraction sheet is an instrument for developing a measurement programme. It helps refine the goal and questions, identify assumptions, and derive metrics systematically. The plan should document the context and the reasoning behind metric selection.

## 9. Worked GQM example: reviews and inspections
The lecture uses an industrial development project:
- Approximately six years
- Around 20 developers
- C++ implementation
- Focus: fault detection and learning effects of reviews/inspections
- Review effort was limited to about four hours per team member per week
- Reviews were intended not only to detect faults but also to help train/onboard engineers.

### Goal
Analyze the effectiveness of structured reviews for the purpose of understanding, with respect to fault detection and learning ability, from the project team's point of view, in the context of the current industrial project.

### High-level questions
- What are baselines/rules of thumb for executing reviews?
- What characteristics of a document lead to optimal review effects?
- What acceptance criteria indicate document quality after review?
- Are reviews useful and efficient for training new engineers?

These are further refined into detailed subquestions. For example, baseline questions examine types of faults found, effort spent, review time, document size, language, complexity, and fault-detection performance.

### Metrics and measurements
Metrics were derived from questions. Examples include:
- Document subsystem
- Document size
- Specification language
- Document complexity
- Effort for a review
- Effort per page
- Number of faults found
- Distribution/severity of faults
- Review date
- Reviewer name
- Other detection mechanisms / whether faults would otherwise have been found

The example includes both direct measurements and identifiers (e.g., document name) needed for later analysis. Several metrics can support multiple questions; some are specific to one question.

### Data collection and interpretation
A data collection form was created and used during reviews. The collected data was later analyzed to answer the questions and interpret the goal. The important lesson is that measurements were planned from the goal rather than chosen arbitrarily.

## 10. Key lessons
- Metrics must be operationally defined and appropriate to the scale.
- A numerical value does not automatically justify arithmetic.
- Context matters when defining metrics.
- GQM links data collection directly to research or improvement goals.
- The goal/questions/metrics chain should be traceable.
- Collecting data without a clear question or goal risks wasted effort and uninterpretable results.

## Source material
- Lecture slides: `Attachments/Slides/RM-ch2-Metrics.pdf`
- Transcripts: Fundamentals of Metrics, Scale Types, GQM, and GQM Example.
