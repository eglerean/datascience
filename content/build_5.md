# **Step 5: Expand the Computer with Remote Storage**

Our computer is now running, and we’ve installed some tools. But soon, we’ll run into a bottleneck: **storage space and speed**.

Research data can grow quickly — especially in fields like genomics, imaging, or environmental monitoring. So we need to expand beyond local disks by using **remote storage**.

## **Why Is Local Storage Sometimes Not Enough?**

Local storage (like an SSD in your laptop or server) is:
- Fast (especially SSDs),
- Always available (no internet needed),
- Limited in size (256 GB to a few TB),
- Vulnerable to failure or theft.

Many datasets in research **exceed local capacity**:
- A single fMRI scan might be 2GB... scale that to 100 subjects and you have 200G... consider that processing requires 5 times the raw MRI data space and we have about 1TB...
- A whole-genome dataset can be over 200 GB,
- Satellite images can reach **terabytes per day**.

## **What Is Remote Storage?**

Remote storage refers to **data stored on another machine** that your computer can access over a network. This includes:
- **Network drives** (e.g., NFS, SMB),
- **Institutional data services** (e.g., CSC Allas object storage),
- **Cloud buckets** (e.g., Amazon S3, Azure Blob),
- **Remote repositories** (e.g., Zenodo, Figshare, institutional archives).

Remote storage can be:
- Much **larger** than local disks,
- **Backed up** by IT,
- **Shared** with collaborators,
- But often **slower** to read/write due to network speed.

## **The I/O Bottleneck**

I/O = Input/Output: how fast data is read from or written to disk.

- **Local SSDs**: Extremely fast (ideal for GPU processing, simulations, etc.).
- **Remote storage**: Depends on internet speed, protocols, and server load. Often slower and less predictable.

If you’re doing **GPU-intensive computation**, reading data too slowly can cause the GPU to sit idle — wasting expensive compute time.

:::{note}
### **Cooking Metaphor: Storage as the Pantry**

- Your **local disk** is the pantry in your own kitchen — fast, private, limited.
- Remote storage is like a **warehouse down the street** — it’s bigger, maybe shared, but slower to access.
- For some tasks, you prep everything from your local pantry.
- For others, you send someone (like `rsync` or a script) to fetch ingredients in bulk.

Choosing where to store your data affects how fast and efficiently your recipe (research) runs.
:::

## **Security and Remote Storage**

Remote storage also brings **data protection considerations**:
- Is the storage **encrypted**?
- Who has **access** to it?
- Is it located in a country with appropriate **legal protections** (important for GDPR)?
- Does it offer **versioning** or **audit logs**?

Trusted research infrastructures (like CSC, SURF, or institutional servers) are often required for **personal or sensitive data**.

:::{note}
# Classification of information and data storage

Many organizations — including universities, research institutes, and government agencies — use a **classification framework** to manage information securely and responsibly. This framework helps determine **where and how different types of data should be stored, accessed, and shared**.

A widely used (though not universal) classification model includes four categories:

1. **Public**  
   Information that is intended for open sharing and has no access restrictions. Examples include published research articles, public websites, and open data. This kind of information can be stored on public servers, shared via email, and posted online without special safeguards.

2. **Internal**  
   Information meant for use within the organization but not intended for public release. It may include internal documentation, draft manuscripts, or general staff communications. Internal data should be stored on organizational platforms (e.g., secure shared drives or institutional cloud services), but doesn’t require encryption or special permissions.

3. **Confidential**  
   Sensitive information that, if exposed, could cause harm to individuals, the institution, or research partners. This includes personal data (e.g., student records, interview transcripts), research data under embargo, or licensed datasets. Confidential data **must be stored in secure environments** — such as encrypted drives, secure servers, or designated trusted research infrastructures — and access must be limited to authorized individuals only.

4. **Secret**  
   Highly restricted information that could result in serious harm if disclosed. It may apply to secondary use of medical data, national security data, defense-related research, or sensitive proprietary data under strict non-disclosure agreements. Secret data typically requires isolated, access-controlled environments with strong encryption and strict auditing.

While this four-level model is common, **each organization may have its own specific definitions, labels, and handling rules** — often aligned with legal or regulatory frameworks (such as GDPR for personal data).

It is essential to **check your institution’s data classification policy** and follow their guidance when deciding:
- Where to store different types of data,
- Who is allowed to access it,
- Whether encryption or special access controls are needed,
- And how data should be shared or archived.

:::


## Bonus Insight for support teams

Support teams are often responsible for:
- Advising on **where data should live** (local vs. remote),
- Managing **access permissions and documentation**,
- Explaining **performance trade-offs** between storage types,
- Ensuring compliance with policies and data management plans (DMPs).

Understanding remote storage — both **practically** and **strategically** — is key to supporting researchers.
