# AdaptiveCacheRL
# 🧠 AI-Assisted Dynamic Cache Replacement Algorithm using Reinforcement Learning

This repository contains the Python implementation and experimental results for the research paper:

> **"AI-Assisted Dynamic Cache Replacement Algorithm using Reinforcement Learning"**  
> *Author: Jerusha*    
> *Year: 2025*

---

## 📘 Overview

Traditional cache replacement algorithms such as **Least Recently Used (LRU)** and **Least Frequently Used (LFU)** rely on fixed heuristics that do not adapt to changing access patterns.  
This project introduces a **Reinforcement Learning (RL)-based adaptive cache replacement policy** using **Q-learning** to dynamically optimize cache performance.

The proposed approach improves **cache hit rate** and **reduces memory access latency** by learning from real-time memory access behaviors.

---

## 🧩 Features

- Implements **Q-learning-based cache replacement** policy  
- Baseline comparison with **LRU** and **LFU** algorithms  
- Synthetic **memory access trace generator**  
- Visualization of **cache hit rate** and **learning convergence**
- Modular, commented, and reproducible Python code

---

## ⚙️ Simulation Setup

| Parameter | Value |
|------------|--------|
| Cache Size | 64 lines |
| Block Size | 32 bytes |
| Access Trace Length | 10,000 |
| Learning Rate (α) | 0.1 |
| Discount Factor (γ) | 0.9 |
| Exploration Rate (ε) | 0.1 |
| Language | Python 3.11 |
| Libraries | NumPy, Matplotlib, Pandas (optional) |

---

## 🧮 Algorithm: Q-Learning Cache Replacement

```text
1. Initialize Q-table for all cache lines (state–action pairs)
2. For each memory access:
     if tag found:
         reward ← +1   (cache hit)
     else:
         reward ← –1   (cache miss)
         replace line with lowest Q-value
3. Update:
     Q(s,a) ← Q(s,a) + α [r + γ max_a' Q(s',a') – Q(s,a)]
4. Continue training until reward convergence
