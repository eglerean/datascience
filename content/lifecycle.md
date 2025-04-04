# Data science on the data life-cycle

-   The data lifecycle considers 7 steps in relationship to data.
-   Each step however could be accompanied with choices of the methods and tools used along with the data
-   Can we expand the considerations that we are familiar with from data management to methods and tools?

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

The cooking analogy for working with data and software - Software \<-\> recipe - Data \<-\> ingredients - Libraries \<-\> pots/tools - Operating system \<-\> style of kitchen we are working with - Hardware \<-\> the actual kitchen with the stove, fridge, cupboards

```{figure} https://coderefinery.github.io/reproducible-research/\_images/recipe.png 
:alt: Cooking recipe in an unfamiliar language 
:width: 50%

Cooking recipe in an unfamiliar language \[Midjourney, CC-BY-NC 4.0\]

```         

```{figure} https://coderefinery.github.io/reproducible-research/_images/libraries.png
:alt: Kitchen with few open cooking books
:width: 50%

When we create recipes, we often use tools created by others (libraries) [Midjourney, CC-BY-NC 4.0]
```

````

## Planning data science work

Planning in data science refers to the deliberate process of defining the goals, scope, data requirements, tools, methods, and risks before diving into code or analysis. It's about **designing the computational and data strategy for a research question** — and ensuring that all decisions (from data collection to modeling) are aligned with research objectives.

In research, proper planning helps:

-   Prevent wasted time due to poor data quality or missing variables.
-   Ensure that ethical and legal responsibilities are considered before doing the actual work (e.g., data protection, consent, licenses).
-   Ensure that the infrastructure can support the analysis (e.g., compute power, storage).
-   Enable reproducibility and collaboration by documenting the project structure early.

Typical activities in the planning phase include: \* Defining research questions: What are you trying to discover, predict, or explain? \* Identifying data needs: Do the needed data already exist? Are new experiments needed? Are there access restrictions? \* Selecting tools and environments: Will the project use Python, R, Jupyter, cloud computing, or local servers? Will a version control system like Git be used? \* Sketching the workflow: Mapping out stages from raw data to results (sometimes visually). \* Identify who can help: colleagues, data stewards, research software engineers, IT staff, domain experts.

::: {note}
### Visualizing workflows in research papers.

![Workflow of data collection and analysis for "Bodily Maps of Emotion (2014)"](https://www.pnas.org/cms/10.1073/pnas.1321664111/asset/dcc3da97-2288-4f1c-a175-cad39b111aab/assets/graphic/pnas.1321664111fig01.jpeg)

From *Nummenmaa, L., Glerean, E., Hari, R., & Hietanen, J. K. (2014). Bodily maps of emotions. Proceedings of the National Academy of Sciences, 111(2), 646-651. https://www.pnas.org/doi/abs/10.1073/pnas.1321664111*
:::

## Collecting data

Data collection is the process of acquiring or generating raw data that will be used in analysis or modeling. In the data science lifecycle, this step is foundational — it defines what you will be able to study, predict, and discover. Poor data collection cannot be fixed later by sophisticated models.

Data can be collected in many forms: \* Structured: Tables, spreadsheets, survey results, sensor logs. \* Unstructured: Text, images, audio, video. \* Semi-structured: JSON, XML, etc.

**Why is this important in research?** Without high-quality, well-documented, and ethically collected data, data science insights are unreliable. For research: \* Validity of conclusions depends on how data were gathered. \* It sets boundaries: “You can only answer the questions your data allow.” \* Poor collection leads to bias, data leakage, or irreproducibility.

**The choice of file formats and data structures** Sometimes we confuse file formats with data formats. It is a bit like confusing the shape of a container of a box of chocolate, with the actual shape of the chocolate pieces inside. Same file formats can contain very different data structures and what is important in computation at the end will be how the data is structured rather than if it is stored in "csv" or "xls".

::: {discussion}
Look at the very long [list of data structures in wikipedia](https://en.wikipedia.org/wiki/List_of_data_structures), some data structures are "low level" and are usually masked to the final user (you do not need to know how a list is stored in a programming language). Other data structures are more general and have become part of the language used in computational sciences: \* Primitive types (fundamental when reading or writing code) \* Composite types (the classic example is a *record* which is the smallest unit of data in a database)
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

**Why this matters in research**:\
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

A comprehensive introduction on the topic with focus on responsible conduct of research is available at https://zenodo.org/records/14032261 and as video at https://www.youtube.com/watch?v=RTHtfGz0-sY
:::

## Data analysis III: qualitative research methods

Qualitative analysis often involves methods like **deductive and inductive coding**. Deductive coding starts with pre-defined categories or theories and applies them to the data, while inductive coding allows themes to emerge naturally from the data itself without prior assumptions. Both approaches help researchers identify patterns, meanings, and insights within textual or observational data, and can also be combined in a flexible, iterative process.

The process for working with qualitative research methods is usually less automated and *automatable* when we compare it with quantitative methods. Recent developements in Natural Language Processing have added the possibility to also automate the coding process, however they might defeat the purpose of qualitative research if the coding is reduced to basic textual classification. It is a currently debated topic in the field of qualitative research (more references coming).

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

## Preserve, Share, Reuse

This stage of the data lifecycle focuses on ensuring that datasets, code, models, and insights from a research project **do not disappear after publication**, but remain accessible and usable for future projects — by yourself, your team, or the broader community.

These steps are closely aligned with the **FAIR principles**:

-   **Findable**: Data and metadata can be located by others.
-   **Accessible**: Data is available under clear conditions.
-   **Interoperable**: Data can be integrated with other systems.
-   **Reusable**: Data is well-described and licensed for reuse.

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
    -   Consider maintaining “model sheets” with version info, training data details, and known limitations.