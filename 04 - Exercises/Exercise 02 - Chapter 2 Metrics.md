# Exercise 02 — Discussion on Chapter 2: Metrics

**Date:** 12.11.2026  
**Course:** Research Methods — Software Systems Engineering, University of Hildesheim  
**Source:** Exercise 2 slides. These are suggested answers and explanations for discussion questions.

## 1. Metrics: examples and classifications

A **metric** is a defined way of characterizing or measuring an attribute of an entity. The meaning of a metric depends on its operational definition: what exactly is measured and how.

| Metric | Possible measure / measurement | Objective or subjective? | Direct or indirect? |
|---|---|---|---|
| Lines of Code (LOC) | Count lines according to a stated rule (e.g., whether comments/blank lines count) | Objective | Direct measure of code size |
| Number of defects | Count defects recorded under a defined classification and reporting process | Objective (the count), though detection/reporting may be influenced by people | Direct measure of recorded defects |
| Development effort | Person-hours/days recorded for a task/project | Objective if recorded consistently | Direct measure of effort |
| Usability | Questionnaire rating or user evaluation | Subjective, if based on users' judgments | Usually indirect, because usability is inferred from responses/behavior |
| Complexity | Complexity score calculated using a defined metric (e.g., cyclomatic complexity) | Objective | An operational measure; complexity is often treated as an indirect characteristic of code |
| Productivity | Output divided by effort (e.g., completed tasks per person-hour) | Objective if both components are defined and recorded | Indirect/derived metric |
| Satisfaction | Rating on a questionnaire | Subjective | Indirect |
| Execution time | Time from a defined start to end event | Objective | Direct |

**Important:** classifications can depend on the precise operationalization. A metric is not automatically objective merely because it produces a number. A subjective judgment can be encoded numerically, such as a Likert rating.

### Why define the measurement procedure?
Different counting rules can produce different values. For LOC, for example, we must decide whether comments, blank lines, or multiple statements on one line count. Without a consistent definition, comparisons may be misleading.

## 2. Why do we need metrics in research?

Metrics help researchers **operationalize concepts and make observations systematic**. They allow us to:
- characterize and compare objects, systems, processes, or people;
- collect data in a defined and repeatable way;
- answer research questions using evidence rather than vague impressions;
- analyze results and communicate findings;
- monitor change or evaluate an intervention.

However, metrics are only useful when they are appropriate for the research goal, clearly defined, and interpreted in context. Measuring the wrong thing—or using an unreliable measurement procedure—can lead to misleading conclusions.

## 3. Scale types — can I calculate the average difficulty?

> Programming problems are classified as easy, medium, hard, and very hard. Can I calculate the average difficulty?

**Generally, not meaningfully if these categories are only ordinal.**

The categories have an order:
- Easy < Medium < Hard < Very hard

But the distances between adjacent categories are not known to be equal. The difference between Easy and Medium might not be equivalent to the difference between Hard and Very hard.

Therefore, an arithmetic mean assumes more information than the ordinal scale provides.

**Appropriate alternatives:** report frequencies/percentages per category, the median category, or mode. If categories are encoded numerically and a defensible equal-distance assumption is explicitly justified, a mean may sometimes be used as an approximation—but that assumption does not come from the ordinal scale itself.

## 4. Scale types — can I say the second product is half as big based on LOC?

> A tool measured LOC for two products. The second has half the LOC of the first. Can I make that statement?

**Yes, if LOC is measured consistently and the counts are comparable.**

LOC is generally a **ratio-scale** metric: there is a meaningful zero (zero lines counted), equal differences are meaningful, and ratios can be interpreted. If product A has 10,000 LOC and product B has 5,000 LOC under the same counting procedure, B has half as many counted lines as A.

**Caution:** LOC is only one operationalization of software size. It does not automatically mean product B is half as complex, half as functional, or half as difficult to develop. The comparison is specifically about the measured LOC.

## 5. Scale types — domain and defect count: can I calculate correlation?

> For each project, I have its domain (aviation, office software, web server, etc.) and its number of defects. Can I calculate whether they correlate?

The two variables have different scale types:
- **Domain:** nominal (categories without an inherent order).
- **Number of defects:** ratio (a count with a meaningful zero).

A conventional Pearson correlation is not appropriate for a nominal variable represented by arbitrary numeric labels. For example, coding Aviation=1, Office=2, Web Server=3 would not create meaningful numerical distances.

But we **can investigate an association** between domain and defect count using methods suitable for the data, such as:
- compare defect-count distributions across domains;
- compare means/medians across groups, if assumptions and study design justify the method;
- use a suitable statistical model for count data;
- use contingency tables if the defect count is categorized, with an appropriate association test.

**Key distinction:** “Cannot calculate Pearson correlation on arbitrary category codes” does not mean “cannot study whether the variables are associated.”

## 6. GQM in research — how can it be useful?

GQM (Goal–Question–Metric) provides a **top-down way to derive what should be measured from a research goal**:
1. Define the goal.
2. Derive questions that help determine whether the goal has been achieved or understand it.
3. Identify metrics that can answer those questions.

Data are then interpreted bottom-up: measurements → metrics → answers to questions → conclusions about the goal.

Although GQM was created to guide improvement in software engineering, it is useful in research because it helps ensure that collected data are relevant to the research question and prevents collecting metrics without a clear purpose.

## 7. GQM exercise — “How can I improve the productivity of my studies?”

### 7.1 Goal using the GQM goal template

**Analyze** my study activities  
**for the purpose of** improving  
**with respect to** study productivity and learning effectiveness  
**from the point of view of** myself as a student  
**in the context of** my university courses, study schedule, and learning activities.

Template components:
- **Object of study:** study activities / study process
- **Purpose:** improve
- **Quality focus:** productivity and learning effectiveness
- **Viewpoint:** the student
- **Environment:** university studies and the student's study context

This is one reasonable formulation; the goal can be refined to focus on a specific course, time period, or type of learning activity.

### 7.2 Possible questions

Questions should operationalize the goal and help explain productivity, not simply collect unrelated data.

1. How much time do I spend studying each week?
2. How much of that time is focused study time versus breaks or distractions?
3. How much course material do I complete per study session or per hour?
4. How well do I retain and understand the material?
5. Which study methods are associated with better learning outcomes?
6. How often do I meet planned study goals?
7. Which factors (sleep, distractions, time of day, study location, task difficulty) may affect my productivity?
8. Does my productivity change over time or between courses?

### 7.3 Possible metrics

| Question | Possible metric | Measurement |
|---|---|---|
| Study time | Total study hours/week | Time log |
| Focus | Focused minutes per session; focus ratio | Session tracking; focused time / total session time |
| Output | Topics, pages, exercises, or tasks completed per hour | Study log with a defined unit of output |
| Learning | Quiz/test score; number of correct answers; retention after a delay | Standardized quiz or self-test |
| Goal achievement | Percentage of planned tasks completed | Completed tasks / planned tasks × 100 |
| Study method | Time and learning outcome per method | Record method used and quiz results |
| Distractions | Number or duration of interruptions | Interruption log |
| Sleep | Sleep duration | Daily record or device data |
| Consistency | Number of study days/week; streaks | Calendar or study log |

**Caution:** “Pages studied per hour” is a productivity measure, but it is not necessarily a measure of learning. Pair productivity metrics with learning-effectiveness metrics to avoid optimizing for superficial output.

### 7.4 Example GQM interpretation

Suppose the data show that:
- study sessions are longer when the phone is away;
- more exercises are completed during focused sessions;
- quiz scores are higher after practice questions than after rereading alone.

These observations may suggest changes to the study routine. But they do not automatically establish causation: other factors could influence the results. A stronger study design could systematically compare methods while controlling or recording relevant factors.

## 8. GQM Abstraction Sheet (example)

The slides introduce four areas of an abstraction sheet: Quality Models, Variation Factors, Baseline Hypothesis, and Impact on Baseline Hypothesis.

### 1. Quality Models
What does “study productivity” mean in this context?
- Efficient use of study time
- Amount of relevant work completed
- Learning and retention
- Achievement of planned goals

### 2. Variation Factors
What may influence productivity?
- Study method
- Topic difficulty
- Prior knowledge
- Time of day
- Sleep
- Distractions
- Study environment
- Breaks
- Motivation

### 3. Baseline Hypothesis
A possible starting assumption to investigate:
> Focused study sessions with fewer distractions are associated with higher study productivity and better learning outcomes than unfocused sessions.

This is a hypothesis to test, not an established fact.

### 4. Impact on Baseline Hypothesis
What evidence would change the hypothesis?
- If focused sessions consistently produce no better output or learning outcomes, the hypothesis may need refinement.
- If results differ by subject or method, the hypothesis may be context-dependent.
- If apparent improvements are explained by prior knowledge or topic difficulty, those factors need to be considered.

## Exam takeaways

- **Metric:** must have a clearly defined measurement procedure.
- **Objective vs. subjective:** depends on whether the value is based on observable rules or judgment.
- **Direct vs. indirect:** direct metrics measure an attribute directly; indirect metrics infer a characteristic from other measurements.
- **Nominal:** categories; no ordering.
- **Ordinal:** order exists, but distances are not known to be equal.
- **Interval:** equal differences, but no true zero.
- **Ratio:** equal differences and meaningful zero; ratios are meaningful.
- **GQM:** Goal → Questions → Metrics; interpretation moves from measurements back toward the goal.
- Never select metrics without knowing the goal and research questions.
- A numerical representation does not automatically make a variable interval or ratio scale.
- Association is not causation.

## Revision checklist
- [ ] Give examples of metrics and classify them.
- [ ] Explain why measurement definitions matter.
- [ ] Explain the role of metrics in research.
- [ ] Identify scale types and which operations they support.
- [ ] Explain why averaging ordinal categories is problematic.
- [ ] Explain why LOC ratios are meaningful (with caveats).
- [ ] Explain why arbitrary nominal codes cannot be used for Pearson correlation.
- [ ] Describe GQM and how it is useful in research.
- [ ] Formulate a GQM goal using all five template components.
- [ ] Derive questions and metrics from a goal.
- [ ] Explain the four parts of the GQM abstraction sheet.
