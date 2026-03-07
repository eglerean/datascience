# Quick Reference

This page provides a concise glossary of key terms used throughout the course. Use it as a reference during or after the workshop.

---

## Data Science Concepts

**Artificial Intelligence (AI)**
The broad field of building computer systems that can perform tasks normally requiring human intelligence — such as recognizing images, understanding speech, or generating text.

**Confirmatory research**
Research that tests a specific, pre-defined hypothesis using appropriate statistical methods. Contrast with exploratory research.

**Data science**
An interdisciplinary field that extracts knowledge and insights from data using statistics, computer science, mathematics, and domain expertise. In research, often called *data-driven research*.

**EDA (Exploratory Data Analysis)**
An approach to analyzing datasets to summarize their main characteristics, often using visualizations, before applying formal statistical models.

**Exploratory research**
Research that explores patterns and generates hypotheses from data, without a specific hypothesis defined in advance. Contrast with confirmatory research.

**FAIR principles**
A set of principles for data stewardship: **F**indable, **A**ccessible, **I**nteroperable, **R**eusable. Widely adopted by funders and journals. See [go-fair.org](https://www.go-fair.org/fair-principles/).

**Machine learning (ML)**
A subset of AI in which systems learn patterns from data to make predictions or decisions, rather than being explicitly programmed with rules.

**Open science**
A movement making scientific methods, data, and outputs freely available and transparent, including open access, open data, open code, and preregistration.

**Registered report**
A publication format in which the study design and analysis plan are peer reviewed and accepted before data collection begins — reducing publication bias and p-hacking.

**Reproducibility**
The ability to re-run an analysis using the original code and data and obtain the same results. Distinct from *replicability* (obtaining the same scientific conclusion from a new independent study).

**Tidy data**
A structured format for tabular data in which each variable has its own column and each observation has its own row. Proposed by Hadley Wickham (2014). Facilitates consistent, automated analysis.

---

## Data Lifecycle Terms

**DMP (Data Management Plan)**
A document describing how research data will be collected, stored, protected, shared, and preserved throughout and after a project. Required by many funders.

**DOI (Digital Object Identifier)**
A persistent, unique identifier assigned to digital objects (papers, datasets, code) to make them permanently citable and findable. Example: `https://doi.org/10.1038/sdata.2016.18`.

**Feature engineering**
The process of creating or transforming variables in a dataset to better capture patterns relevant to analysis or machine learning.

**Metadata**
Data that describes other data — for example, who collected a dataset, when, with what instrument, and under what conditions. Essential for making data FAIR.

**Preprocessing**
Transforming raw data into a clean, consistent, analysis-ready format. Includes handling missing values, removing duplicates, normalizing values, encoding categories, etc.

---

## Computing and Infrastructure

**API (Application Programming Interface)**
A defined set of rules that allows one software system to communicate with another. In research, often used to retrieve data from external services (e.g., NASA APOD, SPARQL endpoints).

**BIOS / UEFI**
Firmware that runs when a computer powers on, before any operating system loads. It performs hardware checks (POST) and decides where to load the OS from.

**Cache memory**
Very fast, small memory located near the CPU that stores frequently accessed data to speed up computation.

**Container**
A lightweight, portable software package that includes an application and all its dependencies, ensuring it runs the same way on any system. Common tools: Docker, Singularity/Apptainer.

**CPU (Central Processing Unit)**
The main processor of a computer — executes program instructions sequentially. Multi-core CPUs can execute multiple tasks in parallel. Often called the "brain" of the computer.

**Disk encryption**
A security mechanism that scrambles data on a storage device so it cannot be read without the correct key, even if the physical device is stolen.

**GPU (Graphics Processing Unit)**
A processor with many small cores optimized for parallel computation — originally for graphics rendering, now essential for AI training and other data-parallel tasks.

**HDD (Hard Disk Drive)**
A traditional storage device using spinning magnetic disks. Slower and more fragile than SSDs, but cheaper per terabyte — often used for archival storage.

**HPC (High-Performance Computing)**
The practice of using powerful computers, often networked clusters, to perform computationally demanding research tasks (simulations, large-scale data analysis, AI training).

**InfiniBand**
A high-speed, low-latency networking technology used in supercomputers to connect compute nodes, enabling efficient parallel processing.

**IP address**
A unique numerical identifier assigned to each device on a network. Used to route data to and from the correct destination.

**Motherboard**
The main circuit board of a computer that connects and enables communication between the CPU, RAM, storage, and other components.

**NIC (Network Interface Card)**
Hardware that connects a computer to a network (wired or wireless), enabling communication and data transfer.

**NVMe (Non-Volatile Memory Express)**
A high-speed protocol for SSDs that significantly outperforms older storage interfaces. Common in modern laptops and research workstations.

**OS (Operating System)**
Software (e.g., Linux, Windows, macOS) that manages computer hardware, runs programs, controls user access, and provides interfaces. Linux dominates in HPC and research server environments.

**Package manager**
A tool that automates installing, updating, and removing software packages and their dependencies. Examples: `apt` (Linux), `conda` (cross-platform, Python/R), `pip` (Python), `brew` (macOS).

**PSU (Power Supply Unit)**
Converts AC electricity from the wall into DC power suitable for computer components.

**RAM (Random Access Memory)**
Fast, temporary memory that holds data actively being processed by the CPU. Cleared when the computer is switched off. More RAM allows larger datasets to be processed in memory.

**Remote desktop**
A technology that allows a user to interact with a computer's graphical interface over a network, as if sitting in front of it.

**Slurm**
A widely used job scheduler for HPC clusters. Researchers submit jobs to a queue; Slurm decides when and on which nodes each job runs.

**SSH (Secure Shell)**
A protocol for securely logging into a remote computer over a network using encrypted communication. The primary tool for accessing HPC systems and remote servers.

**SSD (Solid State Drive)**
A fast, durable storage device using flash memory (no moving parts). Preferred over HDDs for active data processing in research.

**Virtual machine (VM)**
A software-based simulation of a computer. Cloud providers offer VMs that can be created, configured, and deleted on demand.

**VPN (Virtual Private Network)**
Creates an encrypted tunnel between your device and a remote network (e.g., your university), making your computer appear to be on that network. Required for accessing some institutional resources remotely.

**VRAM (Video RAM)**
Memory on the GPU used to store data being processed by the GPU (textures, model weights, etc.). More VRAM is needed for larger AI models.

---

## Version Control and Reproducibility

**Branch (Git)**
A parallel line of development in a Git repository. Allows experimenting with changes without affecting the main version.

**Commit (Git)**
A saved snapshot of a repository at a specific point in time, with a message describing what changed.

**Git**
A distributed version control system that tracks changes to files over time, enabling collaboration and complete history of every modification.

**GitHub / GitLab**
Web-based platforms for hosting Git repositories online. Enable collaboration, issue tracking, and public sharing of code.

**Repository (repo)**
A directory tracked by Git, containing all files and their complete history of changes.

**Workflow manager**
A tool (e.g., Snakemake, Nextflow) that automates and orchestrates multi-step computational workflows, ensuring reproducibility and efficient use of resources.

---

## Data Security and Ethics

**GDPR (General Data Protection Regulation)**
EU regulation governing how personal data is collected, stored, processed, and shared. Applies to any organization handling data of EU residents.

**Informed consent**
A process through which research participants are fully informed about a study's purpose, procedures, risks, and their rights before agreeing to participate.

**IRB (Institutional Review Board)**
A committee that reviews research involving human participants to ensure ethical standards are met. Also called an ethics committee.

**Personal data**
Any information that can directly or indirectly identify a living individual. Includes names, email addresses, health data, location data, and combinations of other data.

**Sensitive data**
Data requiring special protection due to potential harm if disclosed — including personal data, commercially sensitive information, and nationally classified material.

---

## File Formats

| Format | Human-readable | Good for |
|---|---|---|
| **CSV** | Yes | Tidy tabular data, wide compatibility |
| **Parquet** | No | Large tabular datasets, efficient storage |
| **HDF5** | No | Array data (e.g., time series, neuroimaging) |
| **NetCDF** | No | Multi-dimensional scientific data (climate, oceanography) |
| **JSON** | Yes | Semi-structured data, APIs, web applications |
| **Feather** | No | Fast in-memory data exchange (Python/R) |
| **Excel (.xlsx)** | Partial | Small datasets, human review — not ideal for automation |
| **SQL** | No | Relational databases, structured queries |
