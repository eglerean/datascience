# **Step 8: Celebrate! You Now Have Built a Supercomputer!**

Congratulations — you've just walked through the conceptual journey of building a supercomputer!

You started with:
- A single computer and its parts,
- Brought it to life with BIOS and an operating system,
- Installed tools,
- Expanded with remote storage and remote computing,
- And finally, **connected many computers into a coordinated, powerful infrastructure**.

You now understand the **fundamentals of computational research infrastructure** — and the role it plays in modern science.

## **What Comes Next?**

While building the hardware is important, **building understanding is even more powerful**. As a researcher or research supporter, your next steps could include:

### Learn how to *use* supercomputers:
- Connect to login nodes with SSH (Secure Shell),
- Submit jobs with a scheduler (Slurm, PBS, or similar),
- Use environment modules to load specific software versions,
- Explore user guides from national computing centers:
  - [CSC (Finland)](https://docs.csc.fi/)
  - [SURF (Netherlands)](https://servicedesk.surf.nl/wiki/display/WIKI/Snellius)
  - [NeIC (Nordic e-Infrastructure Collaboration)](https://neic.no/)
  - [EuroHPC User Support](https://eurohpc-ju.europa.eu/research-innovation/our-supercomputers_en)

### Learn about version control:

```{figure} img/build_8/git_logo.svg
:alt: Git version control system logo
:width: 30%

Git — the most widely used version control system in research computing. [Git SCM, CC-BY 3.0]
```

**Version control** is arguably the single most important practice for reproducible research computing. Even without writing code, understanding version control helps you:

- Track the history of analysis scripts and research workflows,
- Collaborate without overwriting colleagues' work,
- Roll back to an earlier version if something breaks,
- Document what changed and why — for yourself and for reviewers.

**Git** is the most widely used version control system. You do not need to be a programmer to use it. Key learning resources:

- [CodeRefinery Introduction to Git](https://coderefinery.org/lessons/)
- [Software Carpentry Git lesson](https://swcarpentry.github.io/git-novice/)
- [Aalto Git Crash Course](https://scicomp.aalto.fi/scicomp/git/)

Platforms like **GitHub** and **GitLab** host Git repositories online, enabling collaboration and providing a public home for research code.

### Learn about reproducible environments and workflows:
- Use **containers** (Docker, Singularity/Apptainer) to package your entire software environment.
- Practice setting up automated workflows with **Snakemake** or **Nextflow** — these tools make it possible to run complex pipelines reproducibly.
- Document tools and versions for long-term reproducibility using environment files (`requirements.txt`, `environment.yml`, `renv.lock`).
- Explore **Jupyter notebooks** or **R Markdown / Quarto** for reproducible analysis documents that mix code, output, and narrative.

### Learn about responsible use:
- Understand the legal and ethical frameworks governing your data (GDPR, institutional policies, data classification).
- Know when personal or sensitive data **can or cannot** be processed remotely or on shared infrastructure.
- Get familiar with data access policies, security settings, and audit logging at your institution.
- Consider environmental impact: HPC systems consume significant energy. Use resources efficiently — request only what you need and free up allocations when jobs are done.

### Support researchers:
- Help them write better **data management plans** (DMPs) before projects begin.
- Translate their computational needs into infrastructure requests (storage size, CPU hours, GPU hours).
- Connect them with specialist support services: research software engineers, data stewards, HPC support teams.
- Help them document their workflows so results can be reproduced by others.

## How to ask for help

High-performance computing has a welcoming, collaborative community. No one expects you to know everything — the infrastructure is complex, and asking good questions is a skill in itself.

A practical guide: **["How to ask for help with (super)computers"](https://zenodo.org/records/8392763)** — learn how to describe your problem clearly, provide the information support teams need, and get useful answers faster.

When asking for help, it is useful to include:
- **What you were trying to do** (the goal, not just the error),
- **What you actually did** (the exact commands or steps),
- **What happened** (the full error message, not just "it didn't work"),
- **What you already tried** (so helpers can skip those suggestions).

:::{discussion}
You've built your own kitchen, learned to borrow others, and now you're part of a shared cooking facility where world-class science happens.

You're not just a user of tools — you help **design kitchens**, **organize workflows**, and **support researchers** in creating sustainable, powerful recipes for discovery.

What is one concept from this episode series that you found most surprising or most useful? What would you like to learn more about?
:::

## Remember: you are never alone

High-performance computing is a diverse community of people with various expertise who are very happy to discuss research data analysis workflows and decide together which tool is the most suitable for which case.

Key communities and resources:
- **CodeRefinery** (https://coderefinery.org): Free workshops on version control, reproducibility, and research software.
- **The Carpentries** (https://carpentries.org): Community-driven workshops on software and data skills for researchers.
- **Research Software Engineering communities**: RSE societies in many countries connect researchers with software engineering expertise.
- **HPC support teams** at your national computing center: They exist to help researchers use infrastructure effectively.

:::{keypoints}
- A supercomputer is built incrementally — from single components to networked, parallel systems.
- Version control (Git) is one of the most important practices for reproducible and collaborative research.
- Reproducible environments (containers, workflow managers) ensure your analysis can be re-run by others.
- Responsible use includes understanding data policies, security, and environmental impact of computing.
- You are never alone — the research computing community is collaborative and supportive.
:::
