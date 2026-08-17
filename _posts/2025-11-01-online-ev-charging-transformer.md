---
title: "Detecting EV charging events online with a memory-augmented transformer"
date: 2025-11-01
permalink: /posts/2025/11/online-ev-charging-transformer/
tags:
  - electric vehicles
  - transformers
  - time series
  - smart meters
---

Distribution networks in Australia are seeing more electric vehicles every year, and network operators need to know, in near real time, when and where charging events happen. Smart-meter data offers the raw signal, but EV charging looks a lot like other high-power appliances (heat pumps, kettles, ovens) once the meter aggregates everything at the household level.

In our paper in *Applied Energy* (2025) we treat this as an **online event detection** problem on a time series. The core idea is a memory-augmented transformer that keeps a compact bank of past patterns and attends over them as new smart-meter samples arrive. The memory gives the model a longer effective context than the raw input window, and the attention lets it match the current signal against a small set of "prototype" charging shapes learned during training.

Two design choices matter in practice. First, the model runs in a streaming setting, so decisions have to be made without seeing the end of a session. We train with a causal mask and evaluate on rolling windows to match this. Second, we keep the memory small so the model can run inside a utility's edge or gateway stack, not just in a research notebook.

The method sits behind part of the NexusCharge project with ABB Australia and the ARC Linkage electrification program with AGL, AusNet, and SpendWatt.

**Reference.** Kamoona A.M., Lazarevic L., Al Khafaf N., Ali S.M.N., Jalili M., Razzaghi R. Online electric vehicle charging detection based on a memory-augmented transformer architecture. *Applied Energy*, 377, 124549, 2025.
