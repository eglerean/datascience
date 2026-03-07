# Instructor's guide

## Why we teach this lesson

This course exists because researchers increasingly work in data-intensive environments — but many of them, and especially those who *support* researchers (data stewards, research coordinators, IT support, research managers), lack a shared vocabulary and conceptual framework for understanding what data science actually involves.

The goal is **not** to teach programming or hands-on data analysis. Instead, we aim to:

- Give non-technical participants a mental model of how data science works and what infrastructure is involved.
- Help research support staff communicate more confidently with data scientists, IT teams, and researchers.
- Bridge the gap between domain expertise and computational research methods.
- Encourage a culture of FAIR data, reproducibility, and responsible computing from the start of research projects.

This course is designed for half-day to full-day delivery, depending on how much time is devoted to discussions and exercises.

---

## Intended learning outcomes

By the end of this course, participants should be able to:

1. **Define data science** and distinguish it from traditional scientific inquiry and statistics.
2. **Recognize the difference** between exploratory (data-driven) and confirmatory (hypothesis-driven) research.
3. **Navigate the research data lifecycle** (Plan → Collect → Process → Analyse → Preserve → Share → Reuse) and identify where data science methods are applied at each stage.
4. **Explain FAIR data principles** (Findable, Accessible, Interoperable, Reusable) and why they matter for research outputs.
5. **Describe the key components** of a computer (CPU, GPU, RAM, storage, NIC) and how they relate to research tasks.
6. **Understand the role of software environments**, package managers, and containers in reproducible research.
7. **Distinguish between remote computing options**: cloud VMs, HPC clusters, and supercomputers, and when each is appropriate.
8. **Recognize the importance of data security** and classification when working with sensitive research data.
9. **Identify key practices** for reproducible and transparent research: version control, tidy data, open licensing.
10. **Know where to go for help**: computing centers, data stewards, research software engineers, and community resources.

---

## Timing

### Half-day (3 hours)

| Time | Topic |
|---|---|
| 0:00–0:15 | Welcome, icebreaker discussion (What is your research area and what data does it involve?) |
| 0:15–0:40 | Episode 1: What is data science? |
| 0:40–1:20 | Episode 2: Data science lifecycle (condensed — focus on Plan, Analyse, Preserve/Share) |
| 1:20–1:30 | Break |
| 1:30–2:00 | Episode 3: Building a supercomputer — Steps 1–4 (hardware through software) |
| 2:00–2:30 | Episode 3: Building a supercomputer — Steps 5–8 (remote computing through HPC) |
| 2:30–2:50 | Tidy data section (exercise) |
| 2:50–3:00 | Wrap-up, questions, next steps |

### Full day (6 hours)

| Time | Topic |
|---|---|
| 9:00–9:15 | Welcome and icebreaker |
| 9:15–10:00 | Episode 1: What is data science? (full discussion + registered reports) |
| 10:00–11:00 | Episode 2: Data science lifecycle — Plan, Collect, Process, Analyse |
| 11:00–11:15 | Break |
| 11:15–12:00 | Episode 2 continued — Qualitative methods, Ethics, Visualisation, Preserve/Share/Reuse |
| 12:00–13:00 | Lunch break |
| 13:00–14:00 | Episode 3: Building a supercomputer — Steps 1–4 |
| 14:00–15:00 | Episode 3: Building a supercomputer — Steps 5–8 |
| 15:00–15:15 | Break |
| 15:15–15:45 | Tidy data section (exercise) |
| 15:45–16:00 | Wrap-up, questions, next steps, resources |

---

## Preparing exercises

### Before the session

- **Excel exercise** (lifecycle.md): Download the census dataset referenced in the exercise and test that it works with your local Excel or LibreOffice installation. The dataset must be accessible from participant devices. Have a backup link or local copy available.
- **RDMKit discussion**: Open the [RDMKit website](https://rdmkit.elixir-europe.org/) and familiarize yourself with its structure so you can guide participants who explore it.
- **R-graph-gallery**: Open https://r-graph-gallery.com/ in your browser so you can project it during the visualization exercise.
- **Tidy data exercise**: The library book dataset is self-contained — no external resource needed. Ensure you can display the tables clearly.

### Day of the session

- Ensure all participants can access course materials (either online or printed).
- If running in-person, check that the room has stable internet access (required for the RDMKit discussion and YouTube video on CPUs vs. GPUs).
- For the CPU vs. GPU video in build_1.md, test the YouTube embed in your presentation environment beforehand; some institutional networks block YouTube.

---

## Other practical aspects

### Audience composition

This course works best with mixed audiences — researchers from different fields alongside research support staff. The diversity generates richer discussion, as participants share different perspectives on the same lifecycle stages.

If the audience is predominantly IT/technical support, you can move more quickly through the hardware sections and spend more time on the support-team implications of each step.

If the audience is predominantly researchers (non-technical), focus on the conceptual framing and the "what this means for my research" aspects rather than technical details.

### Facilitating discussions

The course uses many open-ended discussion prompts. These work best when:
- You give 3–5 minutes of silent individual thinking before group discussion.
- You explicitly invite quieter participants to contribute.
- You write responses on a shared whiteboard or collaborative document (e.g., HackMD, a shared Google Doc, or a physical whiteboard).

### Remote delivery

The course can be delivered entirely online. Tools that work well for remote discussions:
- **HackMD** (https://hackmd.io): Collaborative markdown notes — participants add their thoughts in real time.
- **Mentimeter** (https://www.mentimeter.com): For quick polls and word clouds during icebreakers.
- **Breakout rooms** in Zoom or Teams: For small-group discussions before whole-group sharing.

### Language and jargon

The course is designed for non-experts, but technical terms are sometimes unavoidable. When introducing a new term:
- State clearly that it is jargon and that participants are not expected to have known it already.
- Provide the plain-language definition before using the term.
- Reinforce through metaphor (the cooking metaphors in the course are designed for this purpose).

---

## Interesting questions you might get

**"Is data science just statistics?"**
No, but there is significant overlap. Data science also involves software engineering (writing code), data infrastructure (storage, computing), and domain knowledge. Statistics provides the mathematical foundation for inference and uncertainty; data science is the broader practice of extracting value from data computationally.

**"Do I need to learn to code?"**
This course does not teach coding. However, understanding how code-based workflows work — even without writing code yourself — helps you collaborate with those who do code, evaluate the quality of computational research, and support researchers more effectively.

**"What is the difference between AI and machine learning?"**
Artificial intelligence (AI) is the broad concept of machines performing tasks that normally require human intelligence. Machine learning (ML) is a subset of AI where systems learn patterns from data rather than being explicitly programmed. Deep learning is a further subset of ML using multi-layered neural networks. In practice, these terms are often used interchangeably in popular media, but in research contexts the distinctions matter.

**"Is my data sensitive? Does GDPR apply to me?"**
GDPR applies whenever you process personal data — information that can directly or indirectly identify a living person. This includes names, email addresses, health data, location data, and often also combinations of seemingly innocuous data points. If you are unsure, consult your institution's data protection officer (DPO) or legal team before collecting or sharing data.

**"Our supercomputer access application was rejected — what do we do?"**
National HPC facilities often have advisory services that can help you revise and strengthen your application. The rejection is often not final — it may indicate that the project needs a more specific computational plan, more preliminary results, or a more detailed justification for the resources requested.

**"What if the tool I need isn't available on the HPC?"**
Most HPC systems allow users to install additional software in their home directory using conda or containers (Singularity/Apptainer). If you need system-level changes, contact the HPC support team — they are generally very willing to help with common software requests.

---

## Typical pitfalls

**Pitfall 1: Assuming participants know what a CPU or RAM does.**
The hardware section should be treated as genuinely new material, even for participants with science or engineering backgrounds. Many researchers use computers every day without knowing the difference between CPU and GPU or why RAM matters.

**Pitfall 2: Over-focusing on one section.**
The course covers a lot of ground. It is easy to spend too long on topics that generate lively discussion (like the data lifecycle or ethics) and run out of time for later sections. Use the timing guide and gently redirect if needed.

**Pitfall 3: The cooking metaphor landing poorly.**
Most participants find the cooking metaphors accessible and fun. Occasionally someone finds them too simplistic or distracting. If this happens, offer the "straight" technical explanation alongside the metaphor and let participants choose what resonates with them.

**Pitfall 4: Participants who are more technical than expected.**
If some participants are already highly technical (e.g., experienced software developers or HPC users), acknowledge their expertise and invite them to share their perspective during discussions. Avoid talking over them or making them feel the course is too basic — their perspective enriches the experience for others.

**Pitfall 5: Treating the tidy data exercise as trivial.**
The library book tidy data exercise is deliberately simple so everyone can engage with it. However, connecting it to participants' own messy datasets is where the real learning happens. Ask participants to share one example of a non-tidy dataset from their own field before revealing the solution.
