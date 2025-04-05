# **Step 6: Expand the Computing by Connecting with Other Computers**

Sometimes, our own computer — even with extra storage — **just isn’t enough** to do what we need. Maybe we’re processing too much data, training a large AI model, or need more memory than we physically have.

In these cases, we don’t just expand storage — we expand **computation** by connecting to other computers.

## **Using Remote Computers**

Remote computing means using another machine, typically more powerful than yours, to:
- Run programs,
- Store data,
- Train models,
- Or host services (like dashboards or APIs).

This remote computer could be:
- A **cloud-based virtual machine** (e.g. from CSC, AWS, Azure),
- A **remote workstation** in your institution,
- A **computing node** on a cluster or HPC system,
- Or a **server** that you access over the internet.

You control the remote computer using tools like:
- **SSH** (secure shell, text-based),
- **Remote desktop** (GUI-based),
- **Web interfaces** (e.g. JupyterHub, VS Code in the browser, OpenOnDemand https://www.puhti.csc.fi/public/).


## **Offloading Computation: APIs**

In many modern applications, **your computer is only a front-end**, while the work is done elsewhere.

This is exactly how **APIs (Application Programming Interfaces)** work:
- You send a **request** (e.g. a prompt to ChatGPT),
- The remote system does all the processing,
- You get back a **response** (e.g. a completed sentence).

Other examples:
- Image classification via a web API,
- Weather forecast data fetched from a public government API,
- Research datasets accessed through SPARQL endpoints or RESTful APIs.

Your laptop just handles the input/output — **the thinking happens remotely**.

:::{note}
### An example on the terminal to query a remote API

In research, it's often useful to retrieve data from external services using APIs (Application Programming Interfaces). Many APIs are **RESTful**, meaning they use standard web protocols (like HTTP) and return data in structured formats, such as JSON. You can query these APIs directly from the terminal using a tool like `curl`.

#### An example with the **NASA Astronomy Picture of the Day (APOD)** service. 

This API provides information and metadata about astronomy images curated by NASA.

You can retrieve the latest entry like this:

```bash
curl "https://api.nasa.gov/planetary/apod?api_key=DEMO_KEY"
```

This command sends a GET request to the NASA APOD API using a public test key (`DEMO_KEY`). The response will be in JSON format and includes the image URL, title, date, and explanation:

```json
{
  "date": "2025-04-05",
  "title": "Solar Eclipse from the ISS",
  "url": "https://apod.nasa.gov/apod/image/2504/eclipse_iss.jpg",
  "explanation": "This image from the International Space Station shows..."
}
```

You can save the response to a file for later use:

```bash
curl "https://api.nasa.gov/planetary/apod?api_key=DEMO_KEY" -o apod.json
```

While this example uses a public endpoint, many APIs require authentication via API keys, tokens, or other headers — these can be added with curl options (e.g. `-H "Authorization: Bearer TOKEN"`), which we’ll explore later.

Accessing APIs from the terminal allows researchers to:
- Automate data collection,
- Build reproducible workflows,
- Integrate external scientific datasets directly into analysis pipelines.

:::




:::{discussion}

**Cooking Metaphor: Borrowing Another Kitchen**

Imagine your kitchen is too small for a banquet. You can:
- Rent space at a **larger kitchen across town** (remote machine),
- Hire a **chef robot** that cooks on command (API),
- Or plug into a **remote food factory** using only your computer as a control panel.

Your local computer becomes a **terminal** — a keyboard and a screen — while the real work happens remotely.
:::


## **Cloud Computing and Virtual Machines**

Cloud providers offer **on-demand computing environments**:
- You create a virtual machine (VM) with a few clicks,
- Choose the number of CPUs, RAM, and even GPUs,
- Install your tools, run your code, and shut it down when done.

Cloud platforms include:
- **General-purpose**: AWS, Google Cloud, Azure
- **Research-focused**: CSC

The upside: scale, flexibility, reproducibility.  
The downside: complexity, cost, and security considerations.


## **Security and Compliance**

Using remote systems for research means:
- Being mindful of **who else can access the system**,
- Ensuring **data protection** (especially with personal data),
- Using **strong authentication** (SSH keys, 2FA),
- Following your institution’s **IT and ethical guidelines**.

## Bonus Insight for support teams

As a support person, you’ll often help researchers:
- Understand where to run their code or models,
- Set up SSH access or Jupyter environments,
- Decide between **on-premises** and **cloud-based** resources,
- Comply with **data security and legal requirements** when using external computing power.

You don’t need to be a system administrator — but you *do* need to know what’s possible, what’s allowed, and what questions to ask.
