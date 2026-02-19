#  Bash_Automation_Scripts

A collection of personal **Bash scripts** for quickly launching web tools from the terminal on Ubuntu Linux.

> Built by someone (Umair) learning Linux while pursuing a career in **HPC (High Performance Computing)** and **Quantitative Finance**.

---

## Folder Setup

```bash
mkdir ~/automation_scripts
```

Add the folder to your PATH so scripts work as commands from anywhere:

```bash
nano ~/.bashrc
```

Add this line at the bottom:

```bash
export PATH="$HOME/automation_scripts:$PATH"
```

Save (`Ctrl+O`, `Enter`) and exit (`Ctrl+X`), then reload:

```bash
source ~/.bashrc
```

---

## What is a Bash Script?

A **Bash script** is a plain text file containing Linux terminal commands that run in sequence. It's the Linux equivalent of a Windows PowerShell script (`.ps1`). Bash scripts use the `.sh` extension by convention, but scripts meant to be run as commands (like these) often have **no extension** so you can type them cleanly.

Every Bash script starts with a **shebang** line:

```bash
#!/bin/bash
```

This tells the system to use the Bash shell to run the script.

---

##  How to Create a New Script

**Step 1 — Create and write the script:**

```bash
nano ~/automation_scripts/scriptname
```

Paste this template inside, replacing the name and URL:

```bash
#!/bin/bash
echo "Launching [Name] in your default browser..."
xdg-open "https://yoururl.com" &>/dev/null &
```

- `xdg-open` — the standard Linux command to open a URL in your default browser
- `&>/dev/null` — silences noisy GTK warnings that would clutter your terminal
- `&` at the end — runs the browser in the **background** so your terminal prompt returns immediately

Save with `Ctrl+O`, `Enter`, then exit with `Ctrl+X`.

**Step 2 — Make it executable:**

```bash
chmod +x ~/automation_scripts/scriptname
```

`chmod +x` gives the file **execute permission** — without this, Linux won't run it as a program.

**That's it.** Now just type `scriptname` in any terminal window.

---

##  Scripts in This Repo

| Command | URL | Description |
|---------|-----|-------------|
| `claude` | https://claude.ai | Opens Claude AI |
| `gemini` | https://gemini.google.com | Opens Google Gemini |
| `chatgpt` | https://chatgpt.com | Opens ChatGPT |
| `docs` | https://docs.google.com | Opens Google Docs |

---

##  Why This Matters for HPC & Quant Careers

This project might look simple, but the skills behind it are directly relevant to both fields:

### HPC (High Performance Computing)
HPC clusters like those at universities, research labs, and cloud providers (AWS, Google, Microsoft) run almost entirely on **Linux**. Your entire workflow — submitting jobs, managing files, automating pipelines, monitoring processes — is done through Bash scripts. HPC engineers write Bash scripts daily to automate simulations, schedule jobs with tools like SLURM, and chain together complex computation steps. Starting here builds the muscle memory you'll rely on constantly.

### Quantitative Finance
Quant desks run their infrastructure on Linux servers. Bash scripting is used to automate data pipelines, schedule trading model runs, manage log files, and deploy code. Understanding PATH, permissions (`chmod`), and process management (`&`, background jobs) is foundational knowledge expected of any quant developer or quant researcher working close to the infrastructure layer.

### Skills demonstrated in this project
- Writing and executing Bash scripts
- Managing PATH and shell environment (`~/.bashrc`)
- File permissions (`chmod +x`)
- Background process management (`&`, `&>/dev/null`)
- Organizing reusable tooling — a habit that scales to automation of complex workflows

---

## Useful Commands Reference

```bash
which scriptname        # Find where a script/command lives
chmod +x filename       # Make a file executable
source ~/.bashrc        # Reload shell config without restarting terminal
ls ~/automation_scripts # List all your scripts
cat scriptname          # View contents of a script
```

---

## What's Next

Some ideas to grow this repo:

- Scripts to open project folders in VS Code (`code ~/projects/myproject`)
- A script to update all your tools in one command (`sudo apt update && sudo apt upgrade`)
- Scripts to SSH into remote servers or HPC clusters with one word
- Automating repetitive file management tasks with Python called from Bash
