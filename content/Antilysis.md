---
tags:
  - project
---

I made a Rust library implementing anti-analysis techniques for malware on Windows.

# Background

It started when a classmate and I were developing a [[Windows malware]] for a systems programming class project. The expectation was to develop a simple malware written in C or Rust with one feature (ours was infostealing), but as the project was interesting we decided to take it a little further.

We added techniques for the malware to evade basic AVs. We only implemented techniques against dynamic analysis, as static reverse engineering is hard for Rust binaries. We looked for libraries adding such features on Windows, but only found ones for Linux. We therefore decided to make one ourselves.

Many methods were adapted from a state-of-the-art paper.[^1]

# Features

- Checks for processes of
  - common analysis tools (Wireshark, Process explorer...)
  - VM guest (VMware, Virtualbox, QEMU, Xen )
  - debuggers (WinDbg, OllyDbg, GDB, Procdump...)
- Detects common antivirus sandbox artifacts
- Reverse Turing test: waits for user to left click
- Checks if the mac address matches patterns of known VM mac addresses
- Detects VM related files
- Anti-debugging:
  - Checks the presence of debuggers by reading the Process Environment Block (PEB)
  - Checks the presence of the "\.\NTICE" device (named pipe) which is used to communicate with SoftIce, a Windows kernel debugger
  - Ability to hide thread from debuggers

# The dilemma

I found out Antilysis has been used by a real malware found in the wild. A [report by OALabs](https://research.openanalysis.net/zharkbot/rust/triage/2024/07/07/zharkbot.html) describes a malware using a packer written in Rust that uses Antilysis.

I'm not sure how to interpret this. One one hand, it means the project did reach its goal of providing anti-analysis capacities to Windows programs. On the other hand, I might be indirectly helping illicit activities. Should I continue maintaining this project?

---

[Github](https://github.com/percept-denigrate/antilysis) - [Crates](https://crates.io/crates/antilysis)

[^1]: [Afianian et al. (2018), *Malware Dynamic Analysis Evasion Techniques: A Survey*](https://arxiv.org/pdf/1811.01190)
