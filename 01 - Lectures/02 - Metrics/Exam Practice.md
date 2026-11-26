# Chapter 2 — Exam Practice

## Short-answer questions
1. Why are metrics important to research?
2. Explain the difference between an observation, measurement procedure, and metric.
3. Why is measuring Lines of Code not straightforward?
4. Compare objective and subjective metrics.
5. Compare direct and indirect metrics and give examples.
6. What is the difference between product, process, and people metrics?
7. Define nominal, ordinal, interval, and ratio scales.
8. For each scale, list the meaningful comparisons/operations.
9. Why is numerical coding of ordinal categories insufficient to make them interval?
10. Explain why Likert scales should be treated cautiously.
11. What does GQM stand for and what is its purpose?
12. Explain the top-down and bottom-up aspects of GQM.
13. Name and explain GQM's four phases.
14. State and explain the five elements of the GQM goal template.
15. Why are context-independent metric catalogues often ineffective?
16. Explain how a metric can contribute to more than one question.
17. Summarize the structured-review example from the lecture.

## Scale classification practice
Classify and justify:
- Defect category → nominal
- Severity (minor, major, critical) → ordinal
- Temperature in Celsius → interval
- Time spent reviewing (minutes) → ratio
- Agreement: strongly disagree to strongly agree → ordinal
- Number of defects found → ratio/count, assuming a well-defined counting procedure

## GQM application
**Scenario:** A team wants to improve the maintainability of its software.

**Possible goal:** Analyze the maintainability of Product X for the purpose of identifying improvement opportunities, with respect to change effort and code complexity, from the developers' viewpoint, in the context of Team Y's project.

Possible questions:
1. How much effort is required to implement a change?
2. Which components are most complex?
3. How frequently do changes introduce defects?

Possible metrics:
- Change implementation effort (hours)
- Component size
- Complexity measure (with definition)
- Defects introduced per change
- Change size
- Component identifier

Explain the traceability from goal to questions to metrics.

## Mini mock exam
1. A survey answer is coded 1–5. Is it automatically interval? Explain.
2. A researcher measures “productivity” as LOC/hour. Is it direct or indirect? Why?
3. A team collects 50 metrics but cannot explain how they relate to its improvement goal. What is the GQM problem?
4. A measurement has no agreed procedure. What threat does this create?
5. Explain how GQM would be used to investigate whether code reviews improve defect detection.

## Brief answer key
1. No. Numeric labels alone do not prove equal spacing.
2. Indirect: derived from size and effort.
3. The metric collection is not goal-driven and may be context-insensitive or wasteful.
4. Measurement inconsistency and unreliable/ambiguous results.
5. Define the goal, derive questions (defects detected, effort, review characteristics), derive metrics, collect data, interpret answers and goal attainment.
