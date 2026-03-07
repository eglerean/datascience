# **Step 4: Install the Tools You Are Planning to Use**
Now that our operating system is running, we need to give it **specific abilities**. A base system can open windows and manage files — but it can’t do research yet.

To make the computer useful for science, we need to **install software**.

## **What Is Software Installation?**

Installing software means placing a program and its dependencies on your system so it can be run:
- It may involve downloading files,
- Unpacking or compiling them,
- Configuring settings, and
- Linking them to your operating system.

Examples:
- A climate scientist installs **NetCDF tools** to read weather models.
- A data scientist installs **R and the tidyverse** for statistical analysis.
- A linguist installs **NLTK in Python** for natural language processing.

## **Package Managers and Installers**

Operating systems often come with tools to simplify installation:

- **Linux**:
  - `apt`, `dnf`, `yum`, `conda`, `pip`
- **Windows**:
  - `.exe` installers, Windows Store, Chocolatey
- **macOS**:
  - `.dmg` files, `brew`

Some tools are graphical (click to install), others use the **command line** (important in HPC environments and important for reproducibility).

## **Permissions: Can Everyone Install Software?**

No. In shared or secure systems:
- Only **admins (root)** can install system-wide software.
- Regular users can only install in their **home directory** or via isolated environments.

In research groups or HPC systems, this often means:
- You ask the IT team to install something, **or**
- You use workarounds like **conda environments**, **virtualenv**, or **containers**.


## **Licenses and Access**

Some tools are **open source** — free to use, inspect, and share:
- Python, R, Julia
- QGIS, LibreOffice, Jupyter

Others are **proprietary** or require institutional licenses:
- MATLAB, SPSS, ArcGIS, Microsoft Office

You may have to:
- Register with a license server,
- Use your university VPN,
- Or request access through IT.


:::{note}
**Containers: Software in a Box**

When you can’t install tools normally — or want full control over the environment — you can use **containers**:
- Tools like **Docker** or **Singularity/Apptainer** let you run pre-packaged environments.
- Everything the program needs is inside the container — like a **portable mini-kitchen**.

Use case: A data scientist runs a reproducible analysis inside a Docker container that works the same way on a laptop, cloud server, or supercomputer node.
:::

:::{discussion}
### **Cooking Metaphor: Installing Tools = Equipping Your Kitchen**

- Installing **software** is like choosing your appliances and ingredients.
- Package managers are like a **kitchen supply catalog**.
- Permissions are like **access rules** in a shared kitchen — maybe only the head chef can bring in new knives.
- Containers are **your own mobile kitchen** — everything pre-installed, works the same anywhere.
:::

## Bonus Insight for support teams

Why this matters for your support role:
- Researchers may ask for help installing domain-specific software — or report that “something isn’t working” on a cluster or shared VM.
- You should understand:
  - Why permission errors happen,
  - What alternatives (like `conda` or containers) are available,
  - When to escalate to IT or request a license.

You can help by maintaining a list of pre-approved tools, recommended packages, or links to shared containers.

:::{note}
### Why reproducible software environments matter

When a researcher publishes a paper, anyone trying to reproduce the results needs to use **the same software versions** — not just the same code. Dependencies change over time, and a script that worked in 2022 may fail in 2025 if libraries have been updated or removed.

**Best practices for reproducible environments:**
- Record all installed packages and their versions (e.g., in a `requirements.txt` for Python or `renv.lock` for R).
- Use **conda environments** or **virtualenv** to isolate project dependencies from the system.
- Use **containers** (Docker, Singularity) to capture the complete computing environment.
- Publish the environment configuration alongside your code and data.

This is especially important for long-term projects and for research that others will build upon.
:::

:::{keypoints}
- Software must be installed before it can be used — this involves dependencies, configuration, and permissions.
- Package managers (apt, conda, pip, brew) simplify installation but behave differently on different systems.
- On shared or HPC systems, regular users typically cannot install system-wide software — use conda or containers instead.
- Containers (Docker, Singularity) package software and its dependencies into a portable, reproducible environment.
:::
