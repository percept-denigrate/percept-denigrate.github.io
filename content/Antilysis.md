---
tags:
  - project
---

I made a Rust library implementing anti-analysis techniques for malware on Windows.

It started when a classmate and I were developing a [[Windows malware]] for a systems programming class project. The expectation was to develop a simple malware written in C or Rust with one feature (ours was infostealing), but as the project was interesting we decided to take it a little further. We added techniques for the malware to evade basic AVs. We looked for libraries adding such features on Windows, but only found ones for Linux. We decided to make one ourselves.

I found out Antilysis has been used by a real malware found in the wild. A [report by OALabs]() describes a malware using a packer written in Rust that uses Antilysis. I'm not sure how to interpret this. One one hand, it means the project did reach its goal of providing anti-analysis capacities to Windows programs. On the other hand, I might be indirectly helping illicit activities.