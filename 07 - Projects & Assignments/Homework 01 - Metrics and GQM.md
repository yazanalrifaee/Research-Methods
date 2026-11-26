# Homework 01 — Metrics & Scales and GQM

**Course:** Research Methods — Software Systems Engineering, University of Hildesheim  
**Source:** Homework-01.pdf  
**Related material:** Chapter 2 — Metrics; Exercise 02

These are suggested solutions with explanations. For Task 2, some details are deliberately added because the homework explicitly allows assumptions and identifies them as part of the challenge.

# Task 1: Metrics & Scales

## Scenario

A mobile-app study tracks:
- percentage of assigned tasks completed;
- user satisfaction ratings (1–10) from a post-usage survey;
- rate of errors during tasks;
- time taken for each task.

The researchers calculate average completion rate, correlate satisfaction with task completion, compare error rates across user demographics, and calculate a correlation coefficient between these measures.

## 1a. Metrics, measurement, measures, and classifications

| Metric | Measurement / operational definition | Possible measure | Subjective or objective? | Direct or indirect? | Scale type |
|---|---|---|---|---|
| Task completion rate | Number of successfully completed assigned tasks divided by number of assigned tasks, multiplied by 100 | Percentage (0–100%) per participant or task/session | Objective, assuming success criteria are defined consistently | Direct measure of task performance; calculated/derived from task counts | Ratio |
| User satisfaction | Ask participants to rate their experience using the survey's 1–10 rating scale | Rating 1–10 per participant; summarize with distribution, median, etc. | Subjective | Indirect: satisfaction is a latent perception operationalized through self-report | Ordinal by default |
| Error rate | Count errors during task execution and relate them to an exposure denominator, such as tasks attempted or task time. The precise definition must be specified | Errors per task, errors per participant, or errors per unit time | Objective if errors are defined and recorded consistently | Error count is direct; a rate is derived from count and denominator | Ratio (count/rate with meaningful zero, if defined appropriately) |
| Task completion time | Measure elapsed time from a defined start event to a defined completion event for each task | Seconds/minutes per task | Objective | Direct | Ratio |

### Notes on measurement

- The study must define what counts as a successful task, an error, and the start/end of task timing.
- Error rate needs a denominator and a consistent definition. “Errors per task” and “errors per minute” are different measures.
- A 1–10 satisfaction score is numeric, but that does not automatically make it interval-scaled. The spacing between ratings cannot be assumed equal merely because the numbers are consecutive.
- If a survey scale is explicitly designed and validated as an interval-like composite, researchers may justify certain parametric analyses. The homework's simple 1–10 rating should be treated as ordinal unless an interval assumption is justified.

## 1b. Are the analysis operations allowed?

### Operation 1 — Average task completion rate

**Allowed. Yes.**

Completion rate is a ratio-scale measure (a meaningful zero and meaningful ratios, provided the calculation and denominator are defined consistently). An arithmetic mean of participant-level completion percentages can be calculated.

**Important detail:** The mean of participant percentages is not necessarily the same as the overall pooled completion percentage. The researchers should decide which is appropriate:
- **Mean participant completion rate:** average the individual percentages, giving each participant equal weight.
- **Overall pooled completion rate:** total successful tasks ÷ total assigned tasks, giving participants with more tasks greater weight.

The analysis should state which one is used.

### Operation 2 — Correlation between satisfaction and task completion rate

**Not automatically valid using Pearson correlation.**

- Satisfaction rating (1–10): ordinal, unless equal spacing is justified.
- Completion rate: ratio.

Pearson correlation assumes quantitative values with meaningful numerical distances. Since the satisfaction scale is ordinal by default, Pearson's correlation is not automatically justified.

**Recommended option:** Spearman's rank correlation, which assesses a monotonic relationship using ranks and is suitable for ordinal satisfaction scores paired with quantitative completion rates.

If the researchers make and justify an interval-scale assumption for the satisfaction ratings, Pearson correlation could be considered—but the assumption should be reported and ideally checked with a sensitivity analysis.

**Interpretation caution:** Correlation indicates association, not causation. A correlation does not prove that satisfaction causes better task completion or vice versa.

### Operation 3 — Compare error rates across user demographics

**Potentially allowed, but the method depends on the demographic variable's scale type and how error rate is measured.**

Examples:
- Demographic categories such as user group, gender category, or occupation: typically nominal.
- Age: ratio if measured numerically, or ordinal if grouped into ordered age bands.
- Error rate: quantitative ratio measure.

A categorical demographic variable cannot be treated as a numerical variable by assigning arbitrary codes (e.g., Group A=1, Group B=2, Group C=3) and then using those numbers as though distances were meaningful.

Appropriate approaches may include:
- descriptive summaries of error rates for each demographic group;
- comparisons between groups using a statistical method suitable for the number of groups, distribution, and assumptions;
- regression or other models when suitable and when relevant factors are considered.

The precise test cannot be selected from the homework description alone because the demographic variables, sample size, and distribution are unspecified.

### Operation 4 — Calculate a correlation coefficient between these measures

**A conventional correlation coefficient is not automatically appropriate.**

If “these measures” means correlating error rate with demographic categories:
- for nominal categories, Pearson correlation using arbitrary category codes is inappropriate;
- for ordinal demographics, a rank-based method may be appropriate if the relationship is suitable;
- for numeric age and error rate, a correlation method may be appropriate depending on assumptions and the relationship.

The researchers must identify which demographic variable is being analyzed and choose a method based on its scale type.

### Summary of Task 1b

| Operation | Verdict | Reason |
|---|---|---|
| Average task completion rate | **Allowed** | Ratio-scale values support arithmetic mean, with weighting choice stated |
| Satisfaction ↔ completion correlation | **Not automatically with Pearson** | Satisfaction is ordinal by default; Spearman is a suitable alternative |
| Compare error rates across demographics | **Can be done with suitable group-comparison methods** | Method depends on demographic scale, groups, sample, and assumptions |
| Correlation coefficient with demographic categories | **Not valid if nominal categories are arbitrarily coded** | Nominal codes have no numerical meaning |

---

# Task 2: GQM — Is LOC a good metric for software complexity?

## 2.1 Study goal using the GQM goal template

**Analyze** software classes and methods  
**for the purpose of** evaluating  
**with respect to** how well Lines of Code (LOC) represents software complexity  
**from the point of view of** a project manager of a software development company  
**in the context of** the company's software projects and components.

| GQM component | Definition |
|---|---|
| Object of study | Classes and methods in software components |
| Purpose | Evaluate LOC as a metric/proxy |
| Quality focus | Complexity |
| Viewpoint | Project manager |
| Environment | Software development company's projects |

## 2.2 Refine the problem

LOC measures code size, not complexity directly. Larger code may sometimes be more complex, but a short method can be highly complex (e.g., deeply nested logic), while a long method may be relatively straightforward.

The study should therefore investigate whether LOC is:
1. associated with other meaningful complexity indicators;
2. useful for identifying complex classes/methods;
3. useful to the project manager for decisions (e.g., review effort, maintenance, refactoring priorities).

## 2.3 Possible research questions

**RQ1:** How strongly is LOC associated with other complexity measures for classes and methods?

**RQ2:** How well does LOC identify classes or methods considered complex by developers or reviewers?

**RQ3:** Does LOC provide useful information about maintenance-related outcomes, such as defects or change effort, beyond other complexity measures?

**RQ4:** Does the relationship between LOC and complexity differ between classes and methods, or across programming languages/projects?

These questions are examples and may be narrowed based on feasibility and the company's goals.

## 2.4 Possible metrics

### Size metric
- **LOC:** number of source-code lines counted using a clearly defined rule.
- Define whether blank lines, comments, generated code, declarations, and multiple statements per line are included.
- Report LOC at method and class level.

### Additional complexity-related metrics

To avoid treating LOC as the only measure of complexity, compare it with other indicators, such as:

- **Cyclomatic complexity:** number of independent paths through a method's control flow.
- **Nesting depth:** maximum or average nesting of control structures.
- **Coupling:** dependencies on other classes/components.
- **Cohesion:** how strongly the elements of a class relate to a common responsibility (using an appropriate defined metric).
- **Number of methods/fields:** structural characteristics at class level.
- **Developer/reviewer complexity rating:** subjective rating collected using a defined questionnaire or rubric.
- **Maintenance outcomes:** number of defects, change effort, or time spent modifying the unit, if available and appropriately defined.

No single comparison metric should be treated as the absolute truth. Complexity is a multi-dimensional construct, so the study should triangulate multiple indicators.

## 2.5 GQM questions and associated metrics

| GQM question | Metrics / data |
|---|---|
| Q1: How large are the classes and methods? | LOC per method/class; distribution; median and range |
| Q2: How structurally complex are the methods? | Cyclomatic complexity; nesting depth |
| Q3: How structurally complex are the classes? | Number of methods/fields; coupling; cohesion measure |
| Q4: How do LOC and other complexity metrics relate? | Correlations between LOC and each complexity metric |
| Q5: Does LOC identify units judged complex by developers? | LOC; independent developer/reviewer complexity rating; agreement or predictive performance |
| Q6: Is LOC associated with maintenance difficulty? | LOC; defects; change effort; modification time (if available) |
| Q7: Are relationships consistent across contexts? | Metrics grouped by project, language, component, class vs method, and other context variables |

## 2.6 Measurement and data collection plan

### Step 1 — Select the sample
Select a defined set of company projects/components. Consider:
- programming language;
- project age and size;
- application domain;
- development team;
- whether code is production, prototype, generated, or test code.

Avoid selecting only unusually large or complex components.

### Step 2 — Define units of analysis
Analyze at two levels:
- **Method level**
- **Class level**

Do not mix these levels without accounting for their differences.

### Step 3 — Define measurement procedures
Use automated tools where possible, and document:
- LOC counting rules;
- tool/version/configuration;
- treatment of generated code and test code;
- definitions for complexity metrics;
- how missing or exceptional cases are handled.

### Step 4 — Collect the metrics
For each method/class, collect LOC and the selected comparison metrics. If using developer ratings:
- create a clear rating rubric;
- have multiple reviewers rate a subset or all units independently;
- avoid showing LOC to raters if possible, to reduce bias;
- measure reviewer agreement.

### Step 5 — Collect contextual information
Record relevant context such as project, language, component, and unit type. These may influence complexity and help interpret results.

### Step 6 — Analyze the data
Possible analyses:
- descriptive statistics and distributions for each metric;
- scatter plots of LOC against complexity indicators;
- Spearman correlation for ordinal ratings or when a rank-based relationship is appropriate;
- Pearson correlation when quantitative-scale and assumptions are justified;
- compare LOC's ability to identify high-complexity units against alternative metrics;
- investigate whether relationships differ by project, language, or unit type.

If the study uses predictive models, separate training and evaluation data appropriately to avoid evaluating a model on the same data used to fit it.

## 2.7 Possible hypotheses

**H1:** LOC is positively associated with cyclomatic complexity at method level.

**H2:** LOC is positively associated with structural complexity indicators at class level.

**H3:** LOC alone is less informative about developer-perceived complexity than a combination of LOC and other structural metrics.

These are testable hypotheses—not assumptions that must be true.

## 2.8 Interpretation and decision

LOC should not be declared “good” or “bad” based on one correlation alone.

Possible outcomes:
- **Strong association:** LOC may be a useful rough proxy in the studied context, but it is not a direct measure of complexity.
- **Weak association:** LOC alone is not a good complexity indicator for that context.
- **Different relationships by context:** LOC's usefulness may depend on language, project, class/method level, or type of software.
- **Association with maintenance outcomes:** could support practical usefulness, but confounding factors and causality must still be considered.

A practical conclusion should state the context and limitations, e.g., “LOC is useful as a simple size indicator, but should be combined with other metrics when assessing complexity.”

## 2.9 Threats to validity / things to ponder

The homework note says identifying additional considerations is an important part of the task. Relevant issues include:

- **Construct validity:** Does LOC actually represent complexity, or only size?
- **Measurement validity:** Are LOC and other metrics measured consistently and correctly?
- **Confounding:** Language, programming style, developer, domain, and project characteristics may affect both LOC and complexity.
- **Selection bias:** Are the sampled projects representative of the company's software?
- **Unit of analysis:** Methods and classes differ; results may not be comparable when mixed.
- **Subjective ratings:** Developer judgments may vary; use a rubric and examine agreement.
- **Tool differences:** Different LOC/complexity tools or settings may produce different values.
- **Distribution:** LOC and complexity metrics may be skewed; consider robust summaries and suitable statistical methods.
- **Correlation vs causation:** A relationship does not show LOC causes complexity.
- **Practical usefulness:** Statistical association alone does not prove LOC helps make better project-management decisions.

## Final conclusion

LOC is easy to measure, repeatable, and useful as a **size metric**. However, size and complexity are related concepts, not identical ones. A GQM-based study should evaluate LOC against multiple complexity indicators and, where possible, practical outcomes such as maintenance effort or developer assessments. The result should be contextualized rather than claiming LOC is universally good or bad.

---

## Quick revision / oral defense

- Why is a satisfaction rating subjective? Because it represents a participant's perception.
- Why is it indirect? Satisfaction is not directly observable; the survey response is an operationalization.
- Why is 1–10 not automatically interval? Numeric labels do not guarantee equal distances between response categories.
- Why is completion rate ratio scale? It has a meaningful zero and ratios can be interpreted under the defined measure.
- Why may Spearman be preferable for satisfaction and completion? It uses ranks and does not require treating ordinal satisfaction scores as interval.
- Why can't nominal demographic codes be correlated as ordinary numbers? The numerical codes are arbitrary and do not represent magnitude or distance.
- What is the weakness of LOC as a complexity metric? LOC measures size; complexity is multidimensional and may not increase proportionally with size.
- What does GQM ensure? Metrics are derived from a goal and questions, so measurement is purpose-driven.
