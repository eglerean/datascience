# **Building a Supercomputer**

In this episode, we try to build a supercomputer — starting from a single computer and scaling it up, step by step. Along the way, we’ll see why researchers use powerful computers and how the infrastructure behind research computing actually works.

![A computing node](https://raw.githubusercontent.com/eglerean/eglerean.github.io/master/files/AComputingNode.svg)
*The architecture of a computer (or computing node)*

```{toctree}
---
caption: How to build a supercomputer
maxdepth: 1
---

build_1.md
build_2.md
build_3.md
build_4.md
build_5.md
build_6.md
build_7.md
build_8.md
```

## **Motivation: Why Do We Need Computers?**

Computers have become essential to research in every field — from physics to philosophy. But why?

The core reasons are speed, automation, and the ability to **store, process, and analyze large amounts of information** quickly and reproducibly. Researchers use computers to perform tasks that would otherwise take months or years to do by hand — or would be too complex to do at all.

:::{discussion}
**Why Do Researchers Use Computers?**

Let’s look at a few examples:

- **In genomics**, computers process the DNA sequences of thousands of individuals, looking for patterns that might explain disease.
- **In climate science**, computers simulate Earth’s atmosphere and oceans to forecast climate change scenarios decades into the future.
- **In linguistics**, researchers use natural language processing (NLP) to analyze the evolution of meaning in massive text archives across centuries.
- **In the humanities**, historians use text mining to analyze themes across thousands of digitized books.
- **In business research**, analysts model customer behavior using time series and recommendation algorithms.

Without computers, these projects would either be **impossible** or so slow that the results would arrive too late to be useful.
:::


### **Automation, Reproducibility, and Exploration**

Computers allow researchers to:
- **Automate repetitive tasks** (e.g. cleaning 10,000 images),
- **Try many different models quickly** (e.g. training 100 regressions with different parameters),
- **Ensure reproducibility**: code and scripts can be reused, shared, and rerun by others with identical results.

This is especially important in modern science, which increasingly depends on **data-driven inquiry** and **transparent methods**.


:::{discussion}
### **Cooking Metaphor: Computers Are Research Kitchens**

Imagine a researcher as a cook, and their ideas as recipes.

- Without a kitchen (computer), the cook is left to chop and stir with bare hands. It’s slow and exhausting.
- With a modern kitchen, tools like ovens (CPUs), food processors (GPUs), and timers (scripts) make cooking fast, repeatable, and precise.
- Just like kitchens, **computers turn raw ingredients (data)** into **finished meals (results)** — following detailed recipes (programs and workflows).

Different research domains need different kitchens: a historian may just need a stovetop, while a physicist might need an industrial food lab. But **everyone benefits from the tools a computer provides.**
:::

### Bonus Insight

Even though researchers come from very different backgrounds, the **basic functions computers provide are universal**:
- Input: Collect or read data,
- Processing: Apply algorithms, filters, or simulations,
- Output: Store, visualize, or share results.

The tools vary — spreadsheets, R scripts, Python notebooks, cloud platforms — but the principles are the same. Learning how to think about computing **systematically and metaphorically** is a first step to becoming a confident data steward.


## **Motivation: Do I Need a Supercomputer?**

Not all research requires a supercomputer — but some does. Whether you need one depends on **what kind of questions you're asking**, **how much data you're working with**, and **how fast you need results**.

### **When Is a Normal Computer Enough?**

For many research tasks, a **well-equipped laptop or desktop** is completely sufficient:
- Analyzing a survey dataset in SPSS or R.
- Writing scripts in Python to clean tabular data.
- Creating visualizations or writing reports.

These are like home-cooked meals — you only need **one cook** in a regular kitchen.

### **When Do You Need More Power?**

Some research tasks **can be split into smaller pieces** and run in parallel — like having **many chefs working at once**, each preparing one part of the meal.

This is where **supercomputers** come in:
- **Molecular simulations**: Thousands of atoms simulated over millions of time steps.
- **Climate modeling**: Regional and global forecasts require solving differential equations for every square kilometer of the Earth’s surface.
- **AI training**: Large language models (LLMs) like GPT-4 require thousands of GPU hours to train.
- **Satellite image processing**: Terabytes of high-resolution images analyzed over large time windows.

Supercomputers allow these tasks to be done **in hours or days instead of months or years** — and often, to be done at all.

:::{discussion}
### **Cooking Metaphor: Do You Need an Industrial Kitchen?**

Imagine you are making:
- One bowl of pasta for yourself → **your laptop is fine**.
- 100 bowls of different pastas for a party → **you need help**, maybe some automation.
- Tens of thousands of portions for a food festival → You need **an industrial kitchen with many chefs working in parallel**, all coordinated.

That’s what a supercomputer is: **many normal computers working together**, connected with high-speed communication, and orchestrated to act like one large kitchen.
:::

### Not All Remote Computers Are Supercomputers

A supercomputer is powerful, but sometimes you just need **a different computer**, not a “super” one.

For example:
- A **remote workstation** at your department could be enough for heavier tasks
- A **server** with more RAM or a better GPU than your laptop, usually on-premises.
- A **remote virtual machine (VM)** hosted in the cloud (e.g. on CSC, AWS, Azure). Servers can also be virtual machines, from the user perspective nothing changes

These can help you:
- Work with large datasets that don’t fit on your laptop,
- Share resources with collaborators,
- Access faster networks or licensed software.

**Remote ≠ Super.** But remote access is still incredibly powerful.

:::{discussion}
### *How to know when I need to scale up to a bigger system?* 

Understanding what you need to solve your computing problems is not trivial. Some questions you might ask yourself at some point in your life:

* **Do I need one or more CPUs to process my data?** *Caveat: not every problem can be parallelised.*
* **Do I need 1 computer with N CPUs or N computers with 1 CPU?** *Caveat: not all code is written to use multiple CPUs*
* **Do I need GPUs?** *Caveat: GPUs require special code/libraries*
* **Do I have tools/code that can be run on multiple CPUs and/or GPUs?** *Caveat: code does not automatically use all the resources you might have at hand*
* **Is the speed to access the data a bottleneck?** *Caveat: the faster the access to the data, the more localised your data is*
* **What level of security my data (and code) need to have?** *Caveat: sensitive data should not be taken outside remote storage locations*

:::

### Key Takeaway for support teams

Research software engineers along with data stewards can help researchers **decide where to run what** with the perspective of the copmuting needed and the data usage. This includes:
- Estimating whether a task needs local or remote computing (e.g. for using larger storage or more secure storage),
- Helping select platforms (e.g. supercomputer, cloud VM, remote workstation),
- Explaining trade-offs (e.g. cost, speed, access, learning curve),
- Ensuring **ethical and legal use** (e.g. personal data on secure servers only).

Understanding the **computational scale of the problem** is a critical support skill.




