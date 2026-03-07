# What is data science?

```{objectives}
- Understanding what is meant with data science in relationship to other types of research paradigms
- Distinguishing between exploratory and confirmatory research
- Recognizing data science as a complement to traditional scientific inquiry
```

## What is data science?

Data science is an interdisciplinary field that focuses on extracting knowledge and insights from data using methods from statistics, computer science, mathematics, and domain-specific knowledge. It involves techniques such as data cleaning, exploratory analysis, statistical testing, and machine learning to answer research questions, generate predictions, and support decision-making.

```{figure} img/datascience/venn_diagram.svg
:alt: Venn diagram showing data science at the intersection of statistics, computer science, and domain knowledge
:width: 70%

Data science sits at the intersection of statistics, computer science, and domain expertise.
```

Data science is a term used both inside and outside academia. In industry, it describes professional roles where data exploration and modeling drive business insights about products, customers, or processes. In research, data science — also called *data-driven research* — provides a computational complement to traditional scientific inquiry. It allows researchers to work with much larger and more complex datasets than was ever possible before.

:::{note}
### Who is a data scientist?

There is no single agreed-upon definition. A data scientist typically combines skills from at least two of the following areas:

- **Statistics and mathematics**: understanding probability, distributions, model fitting, and inference.
- **Computer science and programming**: writing code, managing data pipelines, and automating analysis.
- **Domain expertise**: knowing enough about the research field to ask meaningful questions and interpret results.

In research, these skills are increasingly spread across teams: domain experts, research software engineers, data stewards, and statisticians often work together on the same project.
:::


## What is the scientific method?

The scientific method is the process through which science advances, building on prior knowledge and unifying understanding over time. It played a key role in the Scientific Revolution. The method involves forming hypotheses, making predictions, and testing them through experiments. While often shown as a fixed sequence, it is better understood as a set of general principles that vary in order and application across different inquiries.

```{figure} https://upload.wikimedia.org/wikipedia/commons/thumb/5/5c/The_Scientific_Method_as_an_Ongoing_Process.svg/1024px-The_Scientific_Method_as_an_Ongoing_Process.svg.png
:alt: The scientific method shown as an ongoing cyclic process
:width: 60%

The scientific method as an ongoing process. [Wikimedia Commons, CC-BY-SA 4.0]
```

:::{discussion}
What are the similarities and the differences between data science and the scientific method?

Consider:
- In which step does data science "enter" the traditional scientific method?
- Can data science generate hypotheses, or does it only test them?
- What does reproducibility mean in each framework?
:::

## Confirmatory (hypothesis-driven) versus exploratory (data-driven) research

| Aspect | Exploratory Research | Hypothesis-Driven Research |
| --- | --- | --- |
| **Goal** | Explore patterns, relationships, generate hypotheses | Test a specific, predefined hypothesis |
| **Approach** | Open-ended, data-first | Theory-first, often based on prior literature |
| **Methods** | Visualizations, clustering, dimension reduction, etc. | Statistical tests, regression models, experiments |
| **Common Tools** | EDA (Exploratory Data Analysis), unsupervised ML | Inferential statistics, causal inference methods |
| **Typical Output** | Insights, patterns, questions | Confirmed or rejected hypotheses |
| **Risk of Bias** | Higher (patterns can emerge by chance) | Lower if pre-registered, higher if hypotheses changed after data collection |

:::{note}
Neither approach is "better" — they serve different purposes and are often used together in the same research project. Exploratory work can spark ideas that are later tested with confirmatory methods.
:::

:::{note}
### Have you heard about registered reports?

> *"Which part of a research study do you believe should be beyond your control as a scientist? **The result**.*
> *Which part of a research study do you believe is most important for advancing your career? **The results**"* ([Chris Chambers, slides](https://osf.io/gs6tp/download))

### Registered reports in a nutshell
([source](https://www.cos.io/initiatives/registered-reports))

```{figure} https://cdn.cos.io/media/images/registered_reports.width-800.png
:alt: Flowchart illustrating the two-stage registered report review process
:width: 80%

The registered report workflow: study design and methods are peer reviewed *before* data collection begins. [Center for Open Science]
```

- Prepare manuscript with: Introduction, Proposed Methods & Analyses, and — if applicable — Pilot data with a power analysis (Power > 90%)
- Stage 1 peer review
- **In principle acceptance** after Stage 1 peer review
- Collect and analyze data according to the plan
- Write the report (same Introduction and Methods; Results and Discussion are new; data and code are deposited and made accessible)
- Stage 2 peer review to confirm
- Done!
- Bonus step: include non-planned analyses (exploratory analyses, clearly labelled as such)

*For history about Registered reports please see [Chambers & Tzavella, Nature 2021](https://www.nature.com/articles/s41562-021-01193-7).*

See also [Glerean 2022 "Introduction to Registered Reports"](https://hackmd.io/@eglerean/RegRep).
:::

## Open science and reproducibility

An increasingly important goal in modern research is **open science** — making the methods, data, and results of research freely available so that others can verify, reproduce, and build upon them.

Key principles of open science include:

- **Open data**: Making datasets publicly available (where legal and ethical constraints allow).
- **Open methods**: Publishing code, scripts, and workflows used in analysis.
- **Open access**: Making research publications freely readable by anyone.
- **Reproducibility**: Ensuring that the same analysis, run on the same data, produces the same results.
- **Replicability**: Ensuring that the same findings hold when the study is repeated independently.

:::{note}
Reproducibility and replicability are related but distinct:

- A result is **reproducible** if you can re-run the original code on the original data and get the same numbers.
- A result is **replicable** if a different research group, running their own study with new data, arrives at the same scientific conclusion.

Both matter for scientific trust — but they can fail for different reasons.
:::

Data science supports open science by making analyses **code-based and documented**, which is far more transparent than manual, undocumented procedures.

## Summary

Data science and the scientific method are complementary approaches in doing science with data. While traditionally a strong emphasis was placed on quantitative sciences, the same conceptual approach applies to qualitative research as well.

:::{note}
## The cooking metaphor for data science
We will often use cooking-related metaphors throughout this course.

**Quantitative, Hypothesis-Driven**
>  _Cooking from a strict recipe_: You start with a well-tested recipe (theory), follow exact steps (methods), and test if the result matches expectations (hypothesis).

**Quantitative, Data-Driven (Exploratory)**
>  _Opening the fridge and experimenting_: You don't have a recipe, but you've got lots of ingredients (data). You try combinations, see what patterns emerge, and maybe invent a new signature dish (model or hypothesis).

**Qualitative, Theory-Driven**
> _Get inspired before cooking_: Cooking a creative dish inspired by a culinary philosophy (e.g., vegan, keto, or traditional Japanese).

**Qualitative, Data-Driven**
> _Foraging and inventing a dish_: You explore the landscape (interviews, observations), gather rich ingredients (quotes, themes), and create a new dish (theory) based on what you find.
:::

:::{keypoints}
- Data science is an interdisciplinary field combining statistics, computing, and domain knowledge.
- Exploratory research generates hypotheses; confirmatory research tests them. Both are valuable.
- Registered reports reduce publication bias by separating study design from results.
- Open science practices — open data, open code, reproducibility — make research more trustworthy and efficient.
:::
