# **Step 2: Add Life to the Hardware**

So far, we've assembled the physical components of a computer — the *kitchen* is ready. But a pile of hardware isn’t useful on its own. We need to make it come alive.

This is where **firmware** and **boot systems** come into play.

## **What Is BIOS (or UEFI)?**

```{figure} img/build_2/bios_post.svg
:alt: Illustration of a BIOS/UEFI boot screen showing system initialization
:width: 70%

BIOS/UEFI boot screen — the first software to run when a computer powers on.
```

The **BIOS** (Basic Input/Output System) is a small program stored on a chip on the motherboard. It runs **immediately when the computer is powered on** — before any operating system is loaded.

Modern systems often use **UEFI** (Unified Extensible Firmware Interface), which is an advanced version of BIOS.

## **What Does the BIOS/UEFI Do?**

1. **Power-On Self-Test (POST)**: Checks that components like RAM and keyboard are working.
2. **Initial Setup**: Detects connected drives and peripherals.
3. **Boot Order**: Decides where to look for the system to load next (e.g., SSD, USB stick, network).
4. **Hands Off**: Once a bootloader is found, the BIOS/UEFI gives control to it.

**In short:** The BIOS is the spark that tells the hardware to wake up and start the process of becoming a computer.

### **Is BIOS Enough? No — We Need an Operating System**

The BIOS only prepares the computer to load a **real operating system** (like Linux, Windows, or macOS). Without an OS, your computer can’t:
- Launch programs,
- Manage files,
- Connect to the internet,
- Display a graphical interface.

We’ll install the OS in the next step — but first, let’s talk about early-stage **security**.

### **Security Already Starts Here: Disk Encryption**

At the BIOS/UEFI level, we can:
- Set a password to **prevent unauthorized access to the firmware settings**,
- Enable **disk encryption** to protect data at rest.

**Encryption** scrambles your data using a mathematical key. Without that key, the data is unreadable — even if someone physically steals the disk.

**Think of encryption like a secret spice blend locked in a safe**: even if someone gets the ingredients (data), they can’t cook the same recipe without the key (password or passphrase).

:::{discussion}
**Cooking Metaphor: Lighting the Stove**

- The BIOS is like **turning on the stove and checking the gas** — it prepares everything to start cooking.
- It doesn’t do any cooking itself — but without it, the kitchen is dark.
- Encryption at this stage is like **locking your ingredient cabinet**, so no one can mess with it while you're away.
:::

### Bonus Insight for support teams

Why this matters:
- Researchers working with **sensitive data** (e.g., health, interviews, unpublished results) must **protect their devices** from theft or unauthorized access.
- As a support person, you may be asked how to:
  - Enable disk encryption,
  - Set up secure boot settings,
  - Ensure laptops comply with institutional data protection policies.

Understanding BIOS/UEFI is not about being a technician — it’s about knowing **where trust begins** in the system.

:::{note}
### Common disk encryption tools

- **BitLocker** (Windows): Built-in disk encryption that is widely used in enterprise and institutional settings. Often centrally managed by IT departments.
- **FileVault** (macOS): Apple’s built-in full-disk encryption, enabled easily in System Preferences.
- **LUKS (Linux Unified Key Setup)**: The standard for disk encryption on Linux systems; often set up during OS installation.

Most universities and research institutions **require** that laptops handling sensitive or personal data have full-disk encryption enabled. Check with your IT or data protection office to confirm your institution’s policy.
:::

:::{keypoints}
- The BIOS/UEFI is the first software that runs when a computer powers on; it prepares hardware for the operating system.
- Disk encryption protects data at rest — even if a device is lost or stolen, encrypted data cannot be read without the key.
- Security begins before the OS loads; BIOS settings and encryption are foundational protections.
:::
