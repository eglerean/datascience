# Data science on the data life-cycle

```{objectives}
- Understand the seven stages of the research data lifecycle
- Recognize how computational methods and tools apply at each lifecycle stage
- Identify key practices for preserving and sharing data responsibly
```

The data lifecycle is a framework for thinking about data throughout the entire span of a research project — not just during analysis. Each stage shapes the quality, usability, and longevity of the research output:

- The data lifecycle considers 7 steps in relationship to data.
- Each step is accompanied by choices of methods, tools, and infrastructure.
- Understanding the lifecycle helps researchers, data stewards, and support staff plan more effectively and avoid costly mistakes.

## The Research Data Lifecycle

![RDMkit image](https://rdmkit.elixir-europe.org/images/data_life_cycle.png)

RDMKit defines the data lifecycle with seven stages: **Plan, Collect, Process, Analyse, Preserve, Share, Reuse**. In data science, each stage is tightly coupled with computational and methodological tasks. Each step has some questions to consider and the answers can affect reproducibility, data quality, and scientific impact:

-   Plan – What data will be needed? What tools and infrastructure will be used?
-   Collect – How will data be acquired or generated (e.g., sensors, experiments, scraping)? What data structure / data format will be used?
-   Process – Cleaning and organizing raw data, often using programming and automation.
-   Analyse – Applying statistics or machine learning to test hypotheses or make predictions.
-   Preserve – Storing raw and processed data in a way that allows others (or your future self) to access and use it later.
-   Share – Making data (and often code) available to others, while ensuring legal and ethical compliance.
-   Reuse – Using existing data for new questions, possibly integrating it with other datasets.

Each stage in the lifecycle is computationally enabled — from writing code for data cleaning, to calculating statistics, to automating sharing via data repositories and APIs.

::: {discussion}
### Explore the RDMkit website.

Spend some time with the RDMkit website: Were you already familiar with [RDMkit](https://rdmkit.elixir-europe.org/)? 
:::

::: {exercise}
### How would the software/methods life-cycle look in a field that you are familiar with?

Example: - Neuroscience: Prepare all documents for ethical review and personal data handling, collect data with the MRI scanner, move data from scanner to workstations, convert data to format for analysis, preprocess data so that statistics can be run, run statistical models (common one is the general linear model), make figures of the results (e.g. brain activation maps), share code and aggregated results on dedicated repositories (e.g. NeuroVault), make sure data can be reused (difficult one!) - *add your field / example here*
:::

````{discussion}

The cooking analogy for working with data and software

Research computing follows the same logic as cooking. Once you learn the analogy, it becomes much easier to explain technical concepts to non-experts:

| Research computing | Cooking equivalent |
|---|---|
| **Software / code** | The recipe — a step-by-step set of instructions |
| **Data** | The ingredients — the raw material being transformed |
| **Libraries / packages** | Kitchen tools: pots, pans, a blender — reusable tools others have made |
| **Operating system** | The style of kitchen — the environment where everything takes place |
| **Hardware** | The kitchen itself — the physical space with stove, fridge, and cupboards |

Just as a recipe written in an unfamiliar language is hard to follow even with the right ingredients, **code without documentation is hard to reproduce** — even with the same data. And just as chefs build on techniques from cookbooks (libraries), researchers build on code and methods from others.

````

## Planning data science work

Planning in data science refers to the deliberate process of defining the goals, scope, data requirements, tools, methods, and risks before diving into code or analysis. It's about **designing the computational and data strategy for a research question** — and ensuring that all decisions (from data collection to modeling) are aligned with research objectives.

In research, proper planning helps:

-   Prevent wasted time due to poor data quality or missing variables.
-   Ensure that ethical and legal responsibilities are considered before doing the actual work (e.g., data protection, consent, licenses).
-   Ensure that the infrastructure can support the analysis (e.g., compute power, storage).
-   Enable reproducibility and collaboration by documenting the project structure early.

Typical activities in the planning phase include:

* Defining research questions: What are you trying to discover, predict, or explain?
* Identifying data needs: Do the needed data already exist? Are new experiments needed? Are there access restrictions?
* Selecting tools and environments: Will the project use Python, R, Jupyter, cloud computing, or local servers? Will a version control system like Git be used?
* Sketching the workflow: Mapping out stages from raw data to results (sometimes visually). 
* Identify who can help: colleagues, data stewards, research software engineers, IT staff, domain experts.

::: {note}
### Visualizing workflows in research papers.

![Workflow of data collection and analysis for "Bodily Maps of Emotion (2014)"](https://www.pnas.org/cms/10.1073/pnas.1321664111/asset/dcc3da97-2288-4f1c-a175-cad39b111aab/assets/graphic/pnas.1321664111fig01.jpeg)

From [*Nummenmaa, L., Glerean, E., Hari, R., & Hietanen, J. K. (2014). Bodily maps of emotions. Proceedings of the National Academy of Sciences, 111(2), 646-651.*](https://www.pnas.org/doi/abs/10.1073/pnas.1321664111)
:::

### Data Management Plans (DMPs)

A **Data Management Plan (DMP)** is a formal document that describes how data will be collected, organized, stored, protected, and shared throughout — and after — a research project. Writing a DMP is increasingly required by research funders (such as the European Research Council, Academy of Finland, NIH, and Horizon Europe) before funding is granted.

A typical DMP answers these questions:

- **What data will be collected or produced?** (Types, volumes, formats)
- **How will it be organized and documented?** (File naming conventions, metadata standards)
- **Where will it be stored during the project?** (Local server, institutional cloud, HPC)
- **How will data be backed up and protected?** (Encryption, access controls, security classification)
- **Who will have access to the data during and after the project?**
- **What will happen to the data after the project ends?** (Archive, delete, publish)
- **Will data be shared openly?** (Which repository, which license, when)
- **Are there legal or ethical constraints?** (Personal data, sensitive data, third-party licensing)

:::{note}
### Why funders require DMPs

Research funders invest public money in science and expect that the outputs — data, code, and findings — are **preserved and accessible** so society gets long-term value from that investment. DMPs also encourage researchers to plan ahead, reducing the risk of data loss or compliance issues at the end of a project.

Many universities offer DMP templates and guidance. Tools like [DMP Online](https://dmponline.dcc.ac.uk/) and [Argos](https://argos.openaire.eu/) help researchers write compliant plans.
:::

:::{discussion}
Think of a research project you know (yours or someone else's). What types of data does it produce? Who should be able to access that data — during the project, and 10 years from now? What are the main risks if the data is lost or not documented properly?
:::

## Collecting data

Data collection is the process of acquiring or generating raw data that will be used in analysis or modeling. In the data science lifecycle, this step is foundational — it defines what you will be able to study, predict, and discover. Poor data collection cannot be fixed later by sophisticated models.

Data can be collected in many forms:
* Structured: Tables, spreadsheets, survey results, sensor logs.
* Unstructured: Text, images, audio, video.
* Semi-structured: JSON, XML, etc.

**Why is this important in research?** Without high-quality, well-documented, and ethically collected data, data science insights are unreliable. For research: 

* Validity of conclusions depends on how data were gathered.
* It sets boundaries: “You can only answer the questions your data allow.”
* Poor collection leads to bias, data leakage, or irreproducibility.

**The choice of file formats and data structures** Sometimes we confuse file formats with data formats. It is a bit like confusing the shape of a container of a box of chocolate, with the actual shape of the chocolate pieces inside. Same file formats can contain very different data structures and what is important in computation at the end will be how the data is structured rather than if it is stored in "csv" or "xls".

::: {discussion}
Look at the very long [list of data structures in wikipedia](https://en.wikipedia.org/wiki/List_of_data_structures), some data structures are "low level" and are usually masked to the final user (you do not need to know how a list is stored in a programming language). Other data structures are more general and have become part of the language used in computational sciences:

* Primitive types (fundamental when reading or writing code)
* Composite types (the classic example is a *record* which is the smallest unit of data in a database)
:::

::: {exercise}
Check the **tidy-data** sub-section for understanding what is a tidy dataset and how to convert data into a tidy format.
:::

## Data preprocessing

Data preprocessing is the step of **transforming raw data into a clean, consistent, and analysis-ready format**. It includes everything from fixing typos and handling missing values, to reshaping datasets and engineering new variables. Without it, models and statistics are built on shaky foundations.

Preprocessing typically involves two major tasks:

1.  **Data cleaning**: Removing errors, inconsistencies, or missing entries.

2.  **Feature extraction (or engineering)**: Creating useful variables or representations from raw inputs to help models or visualizations reveal insights.

**Why is it needed in research?**

In real-world data, messiness is the norm: - Measurements might be missing or corrupted. - Categories might be inconsistently labeled (e.g., "Finland", "FIN", "Suomi"). - Time data might use different formats (e.g., DD-MM-YYYY vs MM/DD/YYYY). - Unstructured data (text, images) must be structured into something a model can read.

Preprocessing ensures **validity, accuracy, and comparability**. It is often the **most time-consuming phase** in a data science project — but also one of the most critical.

**Examples across disciplines**:

-   In **clinical studies**, missing patient records are imputed or excluded carefully to avoid bias.

-   In **natural language processing (NLP)**, raw text is lowercased, tokenized, and stripped of stopwords before analysis.

-   In **physics**, sensor drift or noise is corrected by calibration routines and filtering.

-   In **archaeological data**, scanned artifact images are turned into tabular form by annotating features like shape or material.

**Common tasks and tools**:

-   **Missing values**: Remove, fill (impute), or flag them.

-   **Outliers**: Detect values outside expected range (statistical or domain-driven).

-   **Encoding**: Turn categories into numbers (e.g., one-hot encoding for machine learning).

-   **Normalization**: Scale numeric values to a standard range.

::: {note}
Teaching and learning about data cleaning is notoriously difficult because it’s not just about applying standard techniques—it's a context-dependent, messy process that demands analytical thinking, domain understanding, and hands-on experience. [This article by Randy Au](https://www.counting-stuff.com/whys-it-hard-to-teach-data-cleaning-65949948516031001b3512c8/) explains why traditional teaching methods often fall short and highlights the real-world complexity behind what may seem like a simple task.
:::

## Data analysis I: descriptive statistics and statistical testing

Data analysis refers to the methods used to **summarise, explore, and test patterns in data**. In data science, two foundational categories are:

1.  **Descriptive statistics** – Describe what the data looks like.

2.  **Statistical testing** – Infer whether observed patterns are likely to be real or due to chance.

### **Descriptive Statistics**

These summarise and visualise features of the data, such as:

-   **Central tendency**: Mean, median, mode.

-   **Spread**: Standard deviation, range, interquartile range.

-   **Shape**: Skewness, kurtosis, modality (e.g., unimodal vs. bimodal).

-   **Relationships**: Correlations between variables, cross-tabulations, scatter plots.

**Why this matters in research**:

Descriptive statistics help researchers understand the data distribution, spot data entry errors, and guide the selection of further methods. For example:

-   In **clinical studies**, summary tables show average age, blood pressure, and medication use.

-   In **education research**, exam scores are summarised by class or teaching method.

-   In **environmental monitoring**, daily mean temperatures and standard deviations help understand seasonal variation.

### **Statistical Testing**

Statistical tests assess whether observed differences or relationships are likely to be **statistically significant**, given sample variability.

Some common tests:

-   **T-test**: Are the means of two groups significantly different?

-   **Chi-square test**: Are two categorical variables independent?

-   **ANOVA**: Are there differences between three or more groups?

-   **Correlation (Pearson/Spearman)**: How strong is the relationship between two variables?

-   **Regression analysis**: How does one variable predict another?

Statistical testing connects your **data** to your **hypothesis**: it gives you a way to determine whether the evidence supports your theory.

::: {exercise}
### Isn't excel the most useful tool that any data- engineer \| scientist \| steward \| manager \| assistant \| expert should know?

Let's learn excel by doing! Your task is as follow:

-   Download the census dataset and import it in excel (let's pretend it is truly some sensitive dataset about individuals). If you do not have excel installed, Google Sheet provide a convenient web-based alternative. (Note that depending on which account you use with Google, you might not have the rights to upload real research data containing personal data.)
-   Apply a filter to the data so that it is easy for you to have a look at the values in each column
-   Data cleaning: This data has way too much personal identifiers, not really needed for research! Remove (or mark in some way) those columns that can be used to directly identify an individual.
-   Descriptive statistics I : plot an histograms of the column Age
-   Optional - Descriptive statistics II: plot an histograms of the column Age so that exact ages are show in the X axis
-   Descriptive statistics III: calculate the average of the column Age
-   Export/download/save the excel file (only the sheet you worked on) and submit it as homework.
-   Optional task (difficult!): do you think this cleaned version of the dataset could be shared openly? Do you think the histogram with exact ages in X axis could be included in a paper?
-   Optional task (very difficult): What would you do to make sure there are at least 5 individuals with the same age?
:::

**Beyond the basics**:

-   **Effect sizes and confidence intervals**: A statistically significant result (p \< 0.05) might still be unimportant. Always report effect sizes and uncertainty intervals.

-   **Multiple comparisons**: Testing dozens of variables increases the chance of false positives. Use corrections (e.g., Bonferroni, False Discovery Rate) to control error rates.

-   **Assumptions matter**: Many tests assume normal distributions or equal variances. When those don’t hold, non-parametric alternatives (e.g., Mann–Whitney U test) are safer.

-   **Visual diagnostics**: Always pair numerical tests with plots — histograms, box plots, scatter matrices — to catch anomalies or misinterpretations.

**Exploratory vs. confirmatory**: Exploratory data analysis (EDA) looks for patterns. Confirmatory analysis tests predefined hypotheses. Mixing them without care can lead to bias.

## Data analysis II: artificial intelligence and machine learning

**What is machine learning (ML) and artificial intelligence (AI)?**

-   **Artificial Intelligence (AI)** refers to systems that mimic human cognitive functions like learning, reasoning, and problem-solving.

-   **Machine Learning (ML)** is a subset of AI focused on systems that learn from data — improving their performance on a task over time **without being explicitly programmed**.

In a research context, ML is a powerful tool for:

-   **Pattern recognition** (e.g., detecting disease in medical images),

-   **Prediction** (e.g., forecasting species extinction risk),

-   **Classification** (e.g., distinguishing fake news from real news),

-   **Clustering** (e.g., grouping similar genetic expressions),

-   **Recommendation** (e.g., suggesting relevant articles or treatment plans).

Unlike traditional statistical testing, which relies on predefined hypotheses and assumptions, machine learning is often **data-driven, inductive**, and focused on **prediction** or **automation** rather than explanation.

### **Types of Machine Learning**

**Supervised learning** (training with labeled data):

-   **Classification**: Predict categories (e.g., spam vs. not spam).

-   **Regression**: Predict numerical outcomes (e.g., house prices).

**Unsupervised learning** (no labels, discovering structure):

-   **Clustering**: Group similar data points (e.g., market segmentation).

-   **Dimensionality reduction**: Simplify complex datasets (e.g., PCA).

**Examples across disciplines**:

-   **Healthcare**: Predicting patient readmission based on historical data.

-   **Astronomy**: Classifying galaxy types from images.

-   **Literary studies**: Using NLP to identify themes or authorship in large text corpora.

**Ecology**: Modeling animal movements based on GPS and environmental data.

::: {note}
## How do large language models work? How can I use them responsibly in my work?

A comprehensive introduction on the topic with focus on responsible conduct of research is available at [this zenodo link](https://zenodo.org/records/14032261) and as video at Aalto [University Research Services YouTube channel](https://www.youtube.com/watch?v=RTHtfGz0-sY)
:::

## Data analysis III: qualitative research methods

Qualitative research focuses on understanding **meanings, experiences, and social processes** rather than measuring quantities. It is common in social sciences, humanities, health research, and education — and is increasingly combined with quantitative data science methods.

### Types of qualitative data

Qualitative data is typically rich, contextual, and non-numeric:

- **Interviews**: One-to-one conversations exploring a participant's views, experiences, or practices.
- **Focus groups**: Facilitated group discussions that reveal shared or contrasting perspectives.
- **Observations and field notes**: Systematic records of behaviors, environments, or events.
- **Documents and texts**: Policy documents, social media posts, historical records, publications.
- **Images, audio, and video**: Visual and auditory materials analyzed for meaning.

### Common qualitative analysis methods

**Thematic analysis**: Identifying, analyzing, and interpreting patterns of meaning ("themes") across a dataset. It is flexible and can be applied inductively (themes emerge from the data) or deductively (themes are guided by existing theory).

**Content analysis**: Systematically coding and categorizing text or media, often with quantitative elements (e.g., counting how often a theme appears).

**Grounded theory**: Building a theory inductively from data by constantly comparing new data to emerging categories. The theory is "grounded" in empirical evidence rather than prior assumptions.

**Discourse analysis**: Examining how language constructs meaning, identity, and power relationships in texts and speech.

**Narrative analysis**: Focusing on how people use stories to make sense of their experiences.

### Coding in qualitative analysis

Analysis often involves methods like **deductive and inductive coding**:

- **Deductive coding** starts with pre-defined categories or theories and applies them to the data.
- **Inductive coding** allows themes to emerge naturally from the data itself without prior assumptions.
- Both approaches can be combined in a flexible, iterative process.

:::{note}
### Tools for qualitative analysis

Several software tools are designed to support qualitative data management and analysis:

- **ATLAS.ti**, **NVivo**, **MAXQDA**: Dedicated qualitative data analysis (QDA) software for coding, annotating, and exploring text, audio, and video.
- **Taguette**: A free, open-source alternative for qualitative coding.
- **Simple spreadsheets**: Excel or Google Sheets can work for small datasets with straightforward coding schemes.

These tools do not do the analysis for you — they help organize and track the analytical process.
:::

### Qualitative methods and data science

The process for working with qualitative research methods is usually less automated than quantitative approaches. However, recent developments in **Natural Language Processing (NLP)** have added the possibility to automate parts of the coding process — for example, using large language models to suggest codes or identify themes.

This raises important debates in qualitative research: if coding is reduced to automated textual classification, does it still capture the interpretive depth that makes qualitative research valuable? Human judgment, context awareness, and reflexivity remain essential even when digital tools are used.

:::{discussion}
Think of a research question that could be studied qualitatively. What kind of data would you collect? How would you approach coding and analysis? What ethical considerations would arise in collecting that data?
:::

## Research ethics and responsible data science

Ethical considerations are not a bureaucratic hurdle — they are a core part of doing good science. This is especially important in data science, where large-scale data collection and automated decision-making can have significant societal consequences.

### Ethical approval and institutional review

Research involving human participants typically requires **ethical approval** before data collection begins. In Europe and many other regions, this is managed by **Institutional Review Boards (IRBs)** or **ethics committees**. They evaluate:

- Whether the research question justifies the risks to participants.
- Whether **informed consent** will be properly obtained.
- How participant data will be protected and anonymized.
- Whether vulnerable populations (children, patients, marginalized groups) require additional protection.

**Informed consent** means that participants understand what the research involves, what data will be collected, how it will be used, and that they can withdraw at any time without penalty.

### GDPR and personal data

In the European Union (and increasingly worldwide), the **General Data Protection Regulation (GDPR)** sets strict rules for collecting, storing, and processing data about identifiable individuals. Key principles include:

- **Purpose limitation**: Data collected for one purpose cannot be repurposed without consent.
- **Data minimization**: Collect only the data you actually need.
- **Storage limitation**: Do not keep personal data longer than necessary.
- **Security**: Protect personal data from unauthorized access or leakage.
- **Rights of data subjects**: Individuals have the right to access, correct, or delete their data.

:::{warning}
Personal data (names, email addresses, health information, location data, etc.) has special legal protections. Never store personal data on public cloud services, personal laptops, or systems not approved by your institution's data protection officer without explicit authorization.
:::

### Algorithmic bias and responsible AI

Machine learning models can **inherit and amplify biases** present in training data. For example:

- A hiring algorithm trained on historical data may disadvantage women or ethnic minorities if past hiring was biased.
- A medical diagnostic model trained primarily on data from one population may perform poorly on other groups.
- Natural language models can reflect and reproduce stereotypes present in internet text.

Responsible data science includes:

- **Auditing models** for fairness across demographic groups.
- **Documenting datasets** to make known biases explicit (see: datasheets for datasets).
- **Choosing appropriate evaluation metrics** that account for fairness, not just accuracy.
- **Involving affected communities** in the design and evaluation of systems.

:::{note}
Bias in AI is a well-studied and active research area. A key resource is the [Responsible AI practices guide by Google](https://ai.google/responsibility/responsible-ai-practices/) and the academic literature on algorithmic fairness. The EU AI Act (2024) introduces new legal requirements for high-risk AI systems used in research, healthcare, and public services.
:::

## Communicating results

Research findings are only valuable if they are communicated clearly — to fellow researchers, to funders, to policymakers, and to the public. Communication is not a separate "final step" but an ongoing part of the research lifecycle.

### Types of research output

- **Scientific papers**: The traditional output; peer-reviewed and published in journals. Now increasingly expected to link to data and code repositories.
- **Preprints**: Non-peer-reviewed manuscripts shared immediately on platforms like arXiv, bioRxiv, or Zenodo. Accelerates knowledge sharing.
- **Conference presentations and posters**: Share findings with specialist communities.
- **Data publications**: Datasets published with a DOI in repositories like Zenodo, Dryad, or institutional data archives. Increasingly treated as a citable output.
- **Software publications**: Research code published with documentation and a DOI (e.g., via Zenodo + GitHub).
- **Reports and policy briefs**: Non-academic outputs aimed at practitioners, funders, or policymakers.
- **Blog posts and social media**: Increasing communication of science to broader audiences.

### Reproducible reporting

Modern data science encourages **reproducible reports** — documents that combine text, code, and output (figures, tables) in a single file that can be re-executed to regenerate all results from raw data.

Tools for reproducible reporting:
- **Jupyter Notebooks** (Python, R, Julia): Interleave code, output, and narrative.
- **R Markdown / Quarto**: Produce reports, papers, slides, or websites from a single document.
- **Overleaf / LaTeX**: Common in mathematics, physics, and engineering for structured academic writing.

When your report is reproducible, reviewers and readers can verify your results by re-running your code — greatly increasing trust and transparency.

### Writing for different audiences

The same findings often need to be communicated very differently depending on the audience:

| Audience | What they need |
|---|---|
| **Domain specialists** | Technical detail, statistical rigor, comparison with prior work |
| **Interdisciplinary colleagues** | Plain language, conceptual clarity, context |
| **Funders and managers** | Impact, practical applications, budget justification |
| **General public** | Accessible language, clear visual storytelling, real-world relevance |

:::{discussion}
Think of a research finding you know about. How would you explain it to (a) a colleague in the same field, (b) a colleague from a different discipline, and (c) a curious member of the public? What changes? What stays the same?
:::

## Data visualisation techniques

Data visualization is the practice of **translating data into visual formats** — such as charts, graphs, and maps — to help explore, understand, and communicate patterns and insights. In the data science lifecycle, visualization supports **both analysis and *storytelling***.

-   During analysis: used to explore distributions, detect anomalies, and observe relationships.
-   During communication: used to present findings to technical and non-technical audiences.

**Why is it important in research?**

Visualization is essential to:
-   Reveal **trends and outliers** that raw data or statistics may obscure.
-   Support **hypothesis generation** in exploratory analysis.
-   Communicate **complex findings clearly** to collaborators, funders, and the public.
-   Enhance reproducibility — well-documented plots help others verify your results.

**Common types of visualizations**:

-   **Exploratory**:

    -   Histograms and boxplots (distribution),

    -   Scatter plots and heatmaps (relationships),

    -   Line plots (trends over time),

    -   PCA plots (dimensionality reduction).

-   **Explanatory**:

    -   Bar charts, annotated maps, Sankey diagrams, interactive dashboards.

:::{exercise}
Explore all the possible type of plots available at https://r-graph-gallery.com/

* Was there a type of plot that you were not familiar with?
* Did you know that some types of plots can be more biased than others and wrongly lead to conclusions that are actually not supported by the data? (see for example ["Beyond Bar and Line Graphs: Time for a New Data Presentation Paradigm"](https://journals.plos.org/plosbiology/article?id=10.1371/journal.pbio.1002128))
:::

### Principles for effective data visualization

A good visualization reveals the truth in the data — a poor one hides it or misleads. Some principles to keep in mind:

1. **Choose the right chart type** for your data and your message. Bar charts for comparisons, line charts for trends over time, scatter plots for relationships, heatmaps for matrices.
2. **Show variability**: Plot confidence intervals, error bars, or individual data points — not just means. Raw data often tells a richer story than summary statistics alone.
3. **Label clearly**: Every axis needs a label with units. Titles should describe the finding, not just the variable.
4. **Avoid chartjunk**: Remove unnecessary gridlines, 3D effects, and decorative elements that add visual noise without adding information.
5. **Be honest with scales**: Axes that do not start at zero can exaggerate small differences. Logarithmic scales are appropriate for data spanning many orders of magnitude but must be labelled clearly.
6. **Consider colorblindness**: About 8% of men and 0.5% of women have some form of color vision deficiency. Use colorblind-safe palettes (e.g., Viridis, ColorBrewer).
7. **Make it reproducible**: Save the code that generates each figure so it can be updated or corrected later.

:::{note}
### Tools for data visualization

- **Python**: Matplotlib (flexible, publication-quality), Seaborn (statistical plots), Plotly (interactive), Altair (grammar-of-graphics approach).
- **R**: ggplot2 (powerful and expressive, based on the grammar of graphics), Shiny (interactive apps).
- **QGIS / ArcGIS**: For geospatial data and maps.
- **Flourish / Datawrapper**: Accessible web-based tools for non-programmers.
- **Observable / D3.js**: JavaScript-based interactive visualizations for the web.

The choice of tool depends on your field, your team's skills, and whether the visualization needs to be interactive, static, or embedded in a document.
:::

## Preserve, Share, Reuse

This stage of the data lifecycle focuses on ensuring that datasets, code, models, and insights from a research project **do not disappear after publication**, but remain accessible and usable for future projects — by yourself, your team, or the broader community.

These steps are closely aligned with the **FAIR principles** — a set of guiding principles for data stewardship that have been widely adopted by funders, journals, and research institutions worldwide.

### FAIR Data Principles

```{figure} https://upload.wikimedia.org/wikipedia/commons/a/aa/FAIR_data_principles.svg
:alt: Diagram of the four FAIR data principles: Findable, Accessible, Interoperable, Reusable
:width: 70%

The FAIR data principles. Wikimedia Commons, CC-BY-SA 4.0.
```

The FAIR principles were published in 2016 ([Wilkinson et al., Scientific Data](https://www.nature.com/articles/sdata201618)) and define what it means for data to be well-managed and reusable:

**Findable**
Data and metadata should be easy to find — by both humans and machines.
- Assign a globally unique and persistent identifier (e.g., a DOI) to datasets.
- Describe data with rich metadata so it can be indexed and searched.
- Register the metadata in a searchable resource (a data catalog or repository).

**Accessible**
Once found, data should be retrievable — with clear conditions for access.
- Use open, standardized protocols to retrieve data (e.g., HTTP, HTTPS).
- Where full open access is not possible (e.g., sensitive data), metadata should still be accessible so people know the data exists.
- Access conditions (who can request access and how) must be clearly stated.

**Interoperable**
Data should work with other data, tools, and systems.
- Use formal, shared vocabularies and ontologies for describing content.
- Use widely supported file formats that other researchers can open.
- Include qualified references to other datasets where relevant.

**Reusable**
Data should be well enough described and licensed that others can actually reuse it.
- Include rich and accurate metadata describing how, when, and why the data was collected.
- Attach a clear data usage license (e.g., CC BY 4.0, CC0, or a restricted license with a Data Use Agreement).
- Meet community standards for your domain (e.g., BIDS for neuroimaging, Darwin Core for biodiversity data).

:::{note}
**FAIR ≠ Open.** FAIR data can be restricted. What matters is that the conditions for access are clear and discoverable. Sensitive health data, for example, can be FAIR without being openly accessible — the metadata describes it and explains how researchers can apply for access through a secure process.
:::

:::{discussion}
Look at a dataset you know about (or find one on [Zenodo](https://zenodo.org/) or [Figshare](https://figshare.com/)). Is it FAIR? Can you find its DOI? Does it have a license? Is the metadata sufficient to understand what was collected and how?
:::

In data science, "preservation" extends beyond raw data:

In data science, “preservation” extends beyond raw data:
-   Preprocessed/cleaned data,
-   Code used for analysis,
-   Trained models and configurations,
-   Logs, metadata, and computational environments (e.g. container images).


**Why is this important in research?**

-   Enables **replication and verification** of results (scientific integrity).

-   Allows others to **build upon your work** (cumulative knowledge).

-   Satisfies requirements of funders and publishers.

-   Increases **impact and citations**.

-   Saves time: you or your team can reuse workflows or cleaned datasets in future studies.

**Common tools and repositories**:

-   **Data repositories**: Zenodo, Figshare, Dryad, Dataverse, OpenAIRE.

-   **Code repositories**: GitHub, GitLab (with README.md, license, and citations).

-   **Notebooks**: Jupyter/Quarto projects saved with environment metadata (requirements.txt, environment.yml).

-   **Containerization**: Docker/Singularity images to preserve computing environments.

**Model documentation**: Model cards (for models) and datasheets (for datasets).

**Beyond the basics**:

-   **Metadata and documentation**:
    -   Raw data is rarely useful without context. Metadata standards (like Dublin Core, DataCite, or domain-specific schemas) make data understandable and reusable.
    -   Good README files, manifest files, and inline code comments make preservation valuable.

-   **Versioning**:
    -   Use Git (or DVC for data) to track changes. Without versioning, it’s hard to know what version of the data or model a result came from.

-   **Licensing**:
    -   Reuse depends on legal clarity. Use open licenses (e.g., CC BY 4.0 for data, MIT or GPL for code) to allow others to build on your work.
    -   Ensure you have the rights to share what you publish (especially for collaborative or sensitive datasets).

-   **Sensitive data and controlled access**:
    -   For personal data (e.g., patient records, interviews), open sharing is restricted. However, preservation is still essential — use **Trusted Research Environments** or controlled-access repositories with Data Use Agreements (DUAs).

-   **Persistent identifiers and citation**:
    -   Use DOIs for datasets and models to make them citable.
    -   Adopt standards like the Joint Declaration of Data Citation Principles.

-   **Model and dataset governance**:
    -   AI systems require monitoring post-publication. Future stewards might need to update or “unlearn” parts of models if biases or errors are discovered.

### Version control for researchers

**Version control** is the practice of tracking changes to files over time so that you can see what changed, when, and why — and revert to earlier versions if needed. It is one of the most important practices for reproducible and collaborative research.

**Git** is the most widely used version control system. It tracks changes to text files (code, scripts, documentation) and allows multiple people to work on the same project simultaneously without overwriting each other's work.

Key concepts (no programming required to understand them):

- **Repository (repo)**: A folder tracked by Git — a project's complete history of changes.
- **Commit**: A saved snapshot of the project at a point in time, with a description of what changed.
- **Branch**: A separate line of development — useful for trying new approaches without affecting the main project.
- **Merge**: Combining changes from one branch into another.
- **Remote**: A copy of the repository hosted on a service like GitHub, GitLab, or Bitbucket — enabling collaboration and backup.

Why researchers should use version control:

- **Reproducibility**: Every version of your code and analysis is recorded. You can reproduce exactly what you ran six months ago.
- **Collaboration**: Multiple researchers can work on the same project and merge their contributions.
- **Safety**: You never lose work permanently — previous versions are always accessible.
- **Transparency**: The full history of your analysis is visible, supporting open science.
- **Credit**: Contributions are attributed to individuals through commit histories.

:::{note}
You do not need to be a programmer to benefit from version control. Even writing a research protocol in a Word document benefits from tracking versions — though plain text files work much better with Git than binary formats like `.docx`.

Many national computing centers and universities offer Git training. See [CodeRefinery workshops](https://coderefinery.org/) for researcher-oriented Git training.
:::

:::{keypoints}
## Summary: Key practices across the data lifecycle

- **Plan**: Define data needs, tools, ethical requirements, and write a Data Management Plan before you start.
- **Collect**: Use standard formats, document metadata carefully, and consider data quality from the start.
- **Process**: Data cleaning is time-consuming but essential; document every transformation step.
- **Analyse**: Distinguish exploratory from confirmatory analysis; report effect sizes and uncertainty, not just p-values.
- **Visualize**: Choose chart types carefully; show variability; make figures reproducible.
- **Communicate**: Write for your audience; use reproducible reporting tools; publish code alongside findings.
- **Preserve**: Follow FAIR principles; use repositories with persistent identifiers (DOIs).
- **Share**: Choose open licenses where possible; ensure legal compliance for sensitive data.
- **Reuse**: Document your data well enough for your future self and others to understand and build on it.
- **Ethics**: Obtain ethical approval; follow GDPR; audit for bias in models and datasets.
- **Version control**: Use Git (or similar) to track changes to code and documentation throughout the project.
:::
    -   Consider maintaining “model sheets” with version info, training data details, and known limitations.