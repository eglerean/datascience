# **Step 3: Add Usability with the Operating System**

You’ve assembled the computer. You’ve powered it on. The BIOS did its job — and now it’s time to give the machine a personality: an **operating system**.

Without one, the computer is like a kitchen with gas and electricity but **no recipes**, **no tools**, and **no staff**. It’s technically on, but it doesn’t *do* anything.

## **What Is an Operating System (OS)?**

An operating system is software that:
- **Manages hardware**: Memory, disk, CPU, and input/output devices.
- **Runs programs**: Coordinates which code executes and when.
- **Controls user access**: Determines who can do what.
- **Provides interfaces**: Command line, windows, files, folders, menus.

Examples:
- **macOS** (popular in creative and academic work).
- **Windows** (common for desktops),
- **Linux** (used widely in research environments and HPC),


``````{discussion} Kitchen analogy

Just for fun: which operating systems do the following example kitchens represent?
  `````{tabs}
    ````{tab} 1
      ```{figure} https://coderefinery.github.io/reproducible-research/_images/macos.png 
      :alt: Generated image of a kitchen
      :width: 50%

      [Midjourney, CC-BY-NC 4.0]
      ```
    ````

    ````{tab} 2
      ```{figure} https://coderefinery.github.io/reproducible-research/_images/windows.png
      :alt: Generated image of a kitchen
      :width: 50%

      [Midjourney, CC-BY-NC 4.0]
      ```
    ````

    ````{tab} 3
      ```{figure} https://coderefinery.github.io/reproducible-research/_images/linux.png
      :alt: Generated image of a kitchen
      :width: 50%

      [Midjourney, CC-BY-NC 4.0]
      ```
    ````
  `````
``````


## **How Programs Work With the OS**

- When you open a program, the OS loads it into **RAM**.
- The CPU executes the program **instruction by instruction**.
- The OS handles **scheduling**: when each program gets CPU time.
- The OS also provides **system calls** so that programs can talk to devices (e.g., save a file, read a sensor).

So the OS is the **bridge** between raw hardware and usable computing.

## **Users and Roles in the OS**

Operating systems allow **multiple users**. Each user may have different permissions.

- **Root / Administrator**:
  - Full control of the system.
  - Can install software, change user accounts, reconfigure everything.
- **Normal Users**:
  - Limited control — can run software, manage their own files, but not others’.

This separation prevents accidents or security issues (e.g. if you run a malicious program that deletes the main operating system files, user permissions wouldn't let you do that). 

## **Security and Permissions**

The OS uses **file permissions** and **user roles** to:
- Ensure data integrity (users can’t modify each other’s files),
- Maintain confidentiality (research data is private),
- Protect system functionality.

Permissions control:
- Who can read, write, or execute files.
- Who can install or update software.
- Which users can access shared data folders.

Permissions are like **kitchen access badges** — only the head chef can restock the fridge or replace knives, while sous-chefs can use them but not reorder.

:::{note}
### Permissions in the Linux terminal explained

When you list files in a Linux terminal using the command `ls -l`, you’ll see something like this:

```
-rw-r--r--  1 user group  2048 Apr  5 14:32 data.txt
```

Let’s break it down:

- The first part, `-rw-r--r--`, shows the **file permissions**.
- It’s a 10-character string where:
  - The first character indicates the **type** (`-` = regular file, `d` = directory, `l` = symbolic link, etc.).
  - The next 9 characters are split into **three groups of three**:
    - `rw-`: **Owner** permissions (read, write),
    - `r--`: **Group** permissions (read only),
    - `r--`: **Others** (everyone else; read only).

So in this example:
- The **owner** can **read and write** the file,
- The **group** can only **read** it,
- **Others** (any user on the system) can also only **read** it.

If you see something like this for a script:
```
-rwxr-xr-x
```
That means:
- The owner can **read, write, and execute**,
- The group and others can **read and execute**, but **not modify** the file.

You can change these permissions using commands like `chmod`, and change the owner with `chown`.

Understanding these settings is essential when managing access to data and scripts in shared research environments.

:::




:::{discussion}
**Cooking Metaphor: The Operating System Is the Kitchen Manager**

- The OS decides who can use which appliances.
- It makes sure the oven isn't on fire while the dishwasher is running.
- It keeps the pantry organized (file system),
- And ensures everyone follows safety protocols (permissions and users).

Without an OS, you'd just have an empty room full of disconnected appliances.
:::

:::{note}
### The terminal is the most powerful tool

The terminal — also known as the **command-line interface** or **shell** — is one of the most powerful and flexible tools available on a computer, especially in scientific and research computing.

At its core, the shell is a program that provides a **text-based interface** between the user and the operating system. Rather than clicking through menus and windows, users type commands directly to control the computer. This is why it is called a **"shell"** — it wraps around the underlying system and gives users a structured way to interact with it.

There are different kinds of shells (like `bash`, `zsh`, or `fish`), but they all allow the user to execute programs, navigate the filesystem, automate tasks, and combine tools in highly efficient ways.

The terminal is particularly favored by expert users and researchers because it offers:

- **Precision**: Commands can be written and saved exactly, removing ambiguity and allowing for exact replication of tasks.
- **Speed**: Complex or repetitive tasks that would take many clicks in a graphical interface can be done in seconds with a single command or script.
- **Automation**: Workflows can be scripted, making it easy to repeat analyses, preprocess data, or set up entire environments automatically.
- **Remote access**: Shell-based tools like SSH make it possible to work on powerful remote systems or supercomputers as if they were local.
- **Reproducibility**: Everything you do in the terminal can be logged and version-controlled, which is essential for transparent scientific research.

In short, while it may seem intimidating at first, the shell becomes an essential ally for researchers dealing with data, software environments, or computing infrastructure. Learning to use it effectively can significantly increase both productivity and control over computational tasks.

Consider taking [the Shell Crash Course](https://scicomp.aalto.fi/scicomp/shell/)
:::



## Bonus insight for support teams

Why this matters for your role:
- Researchers will ask you **why they can’t install a tool** or **access a folder** — this often comes down to OS permissions.
- In secure environments (e.g., working with personal data), understanding **user roles** and **access controls** is crucial for compliance.
- If you support computational research, you'll often interact with **Linux-based systems** and need to understand how users and files are managed there.
