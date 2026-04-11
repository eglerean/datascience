# **Step 7: Connect Multiple Computers Together to Build the Supercomputer**

Now that you understand how to use one remote computer, it’s time to **scale up**.

A **supercomputer** isn’t one big machine — it’s a **network of many smaller computers (called nodes)** connected with high-speed communication links and managed by special software to behave like one enormous machine.

## **What Is a Supercomputer Made Of?**

A typical supercomputer consists of:

- **Compute nodes**: Each node is like a standalone computer with CPUs, RAM, and sometimes GPUs.
- **Interconnects**: Fast network cables (e.g., InfiniBand) that let the nodes talk to each other with minimal delay.
- **Storage nodes**: Shared data storage for all the nodes to read/write from.
- **Login nodes**: Where users connect to prepare their jobs.
- **Management system**: To monitor hardware, schedule jobs, and manage user activity.

A supercomputer can include **thousands of nodes**, working together.


## **How Does It Work in Practice?**

Researchers **submit jobs** to a queue. These jobs might:
- Simulate complex phenomena (e.g. earthquakes, airflow),
- Process thousands of images or genome files,
- Train huge machine learning models.

A **job scheduler** (like Slurm, PBS, or Torque) decides:
- When the job runs,
- Which nodes to assign,
- How to balance workloads fairly.

Jobs can run in parallel across dozens or hundreds of nodes — **a form of teamwork at digital scale.**

## **High-Speed Connectivity: InfiniBand**

For nodes to work in parallel efficiently, they must communicate very quickly.  
InfiniBand is a specialized networking technology with **very low latency and high bandwidth**, often used in supercomputers.

Unlike Wi-Fi or standard Ethernet, InfiniBand ensures that node-to-node communication doesn’t become the bottleneck.


## **Why Supercomputers Are Shared Resources**

Running and maintaining a supercomputer is expensive and energy-intensive. That’s why most supercomputers:
- Are **shared national or regional infrastructure** (e.g., CSC’s Mahti in Finland),
- Serve **multiple research groups** at the same time,
- Are managed by IT teams and access is granted via applications or merit.

This model is not just efficient — it’s **sustainable and equitable**.

:::{note}
### Understanding parallelisation with a kitchen metaphor

If it takes 20 minutes to cook a pasta from beginning to end, having 4 stoves or even 4 entire kitchens does not mean that you can cook pasta in 20 / 4 = 5 minutes. Some part of the process can be parallelised, but the cook (= the program) needs to know what to parallelise.

See expanded kitchen metaphor [here](https://docs.google.com/presentation/d/16BTILZlUvEzCt6FfMsB9sSZm0PZHHXLBthE5QfoSrjo/edit?usp=sharing) and [here](https://docs.google.com/presentation/d/18bEZ7Dm4NOYuHLgJ_l1XG_hItLFrCgfk6Xr5N0ZYJLs/edit?usp=sharing). There are also video version of those slides under [Aalto Scientific Computing YouTube channel](https://www.youtube.com/channel/UCNErdFO1_GzSkDx0bLKWXOA).
:::


:::{discussion}

**Cooking Metaphor: A Shared Industrial Kitchen**

- Each node is a **kitchen station**, equipped for specific tasks.
- They are connected by **a conveyor belt system** (InfiniBand),
- Coordinated by a **head chef (Slurm)** who decides who cooks what and when.
- Multiple cooking teams share the kitchen, each getting a time slot.

Instead of every research group building their own kitchen, they **share the industrial space** — everyone gets better tools, and no one wastes energy duplicating them.
:::



## Bonus Insight for support teams

Your role could involve:
- Helping researchers access HPC resources (e.g., apply for accounts, get computing quotas),
- Explaining how job scheduling works,
- Clarifying storage policies and best practices,
- Assisting with reproducibility (e.g., using containers or version control in HPC pipelines),
- Navigating the **research governance** around using shared infrastructure.

Supercomputers are powerful — but without good planning and support, they can be hard to use well.
