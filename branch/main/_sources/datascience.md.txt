# What is data science?

```{objectives}
- Understanding what is meant with data science in relationship to other types of research paradigms
- Distinguishing between exploratory and confirmatory research
```

## What is data science?

Data science is an interdisciplinary field that focuses on extracting knowledge and insights from data using methods from statistics, computer science, mathematics, and domain-specific knowledge. It involves techniques such as data cleaning, exploratory analysis, statistical testing, and machine learning to answer research questions, generate predictions, and support decision-making.

Data science is a term also used outside academia to describe those professional roles where data exploration is fundamental to gain insights about products or other metrics that a company is producing. In research, data science -- also called *data-driven research* -- provides a computational complement to traditional scientific inquiry. It allows researchers to work with much larger and more complex datasets than ever before.

![The data science lifecycle - (c) sudeep.co](https://analyticstraininghub.com/wp-content/uploads/2022/10/data-science.png)


## What is the scientific method?

The scientific method is the process through which science advances, building on prior knowledge and unifying understanding over time. It played a key role in the Scientific Revolution. The method involves forming hypotheses, making predictions, and testing them through experiments. While often shown as a fixed sequence, it's better seen as a set of general principles that vary in order and application across different inquiries.

![The scientific method - Wikimedia](https://upload.wikimedia.org/wikipedia/commons/thumb/5/5c/The_Scientific_Method_as_an_Ongoing_Process.svg/1456px-The_Scientific_Method_as_an_Ongoing_Process.svg.png?20161231121344)


:::{discussion}
What are the similarities and the differences between data science and the scientific method?
:::

## Confirmatory (hypothesis driven) versus exploratory (data driven) research

| Aspect | Exploratory Research | Hypothesis-Driven Research | 
| --- | --- | --- | 
| **Goal** | Explore patterns, relationships, generate hypotheses | Test a specific, predefined hypothesis | 
| **Approach** | Open-ended, data-first | Theory-first, often based on prior literature | 
| **Methods** | Visualizations, clustering, dimension reduction, etc. | Statistical tests, regression models, experiments | 
| **Common Tools** | EDA (Exploratory Data Analysis), unsupervised ML | Inferential statistics, causal inference methods | 
| **Typical Output** | Insights, patterns, questions | Confirmed or rejected hypotheses |




:::{note} 
### Have you heard about registered reports?

> *"Which part of	a research	study do you believe should	be beyond your control as a scientist? **The result**.*
> *Which part of	a research study do	you	believe	is most	important	for	advancing	your	career?	**The	results**"* ([Chris Chambers, slides](https://osf.io/gs6tp/download))

### Registered reports in a nutshell
([source](https://www.cos.io/initiatives/registered-reports))
![Registered reports process](https://cdn.cos.io/media/images/registered_reports.width-800.png)
- Prepare manuscript with: Introduction, Proposed	Methods	& Analyses,	and	- if applicable - Pilot data with a power analysis (Power > 90%)
- Stage 1 peer review
- **In principle acceptance** after Stage 1 peer review
- Collect and analyze data according to the plan
- Write the report (basically same Introduction and Methods, Results and Discussion are new; data and code are deposited and made accessible)
- Stage 2 peer review to confirm
- Done!
- Bonus step: include non-planned analyses (exploratory analyses) 

*For history about Registered reports please see [Chambers & Tzavella, Nature 2021](https://www.nature.com/articles/s41562-021-01193-7).*

See also [Glerean 2022 "Introduction to Registered Reports"](https://hackmd.io/@eglerean/RegRep).
:::

## Summary

Data science and the scientific methods are complementary approaches in doing science with data. While traditionally a strong emphasis had been given towards quantitative sciences, the same conceptual approach applies also to qualitative research.

:::{note}
## The cooking metaphor for data science
We will often use cooking related metaphors.

**Quantitative, Hypothesis-Driven**
>  _Cooking from a strict recipe_: You start with a well-tested recipe (theory), follow exact steps (methods), and test if the result matches expectations (hypothesis).

**Quantitative, Data-Driven (Exploratory)**
>  _Opening the fridge and experimenting_: You don’t have a recipe, but you’ve got lots of ingredients (data). You try combinations, see what patterns emerge, and maybe invent a new signature dish (model or hypothesis).

**Qualitative, Theory-Driven**
> _Get inspired before cooking_: Cooking a creative dish inspired by a culinary philosophy (e.g., vegan, keto, or traditional Japanese)

**Qualitative, Data-Driven**
> _Foraging and inventing a dish_: You explore the landscape (interviews, observations), gather rich ingredients (quotes, themes), and create a new dish (theory) based on what you find. 


:::