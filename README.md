# ⚡ Smart Grid Load Balancing using ADMM and MATPOWER

![Amrita University Logo](https://upload.wikimedia.org/wikipedia/en/5/5d/Amrita_Vishwa_Vidyapeetham_Logo.png)

---

## 👥 Team Members  

- **Aparna.A** – CB.SC.U4AIE24206 
- **Jenishaa Bharathi.M** – CB.SC.U4AIE24221 
- **Police Aryan** – CB.SC.U4AIE24241
-  **Pooja N** – CB.SC.U4AIE24242
---

## 📑 Table of Contents  

- [Abstract](#abstract)  
- [Introduction](#introduction)  
- [Methodology](#methodology)  
- [Dataset](#dataset)  
- [Results](#results)  
- [Conclusion](#conclusion)  
- [References](#references)  

---

## 📌 Abstract  

This project presents a distributed optimization framework for smart grid load balancing using the Alternating Direction Method of Multipliers (ADMM). The Optimal Power Flow (OPF) problem is formulated to minimize generation cost while satisfying power balance and operational constraints. Traditional centralized approaches suffer from scalability issues; hence, ADMM is used to decompose the problem into smaller subproblems solved locally at each node. MATPOWER is used for realistic power system simulation. The results demonstrate improved scalability, efficient load distribution, and convergence to optimal solutions.

---

## 📖 Introduction  

Modern power systems are evolving into smart grids with increasing demand, renewable integration, and distributed generation. These changes introduce challenges such as:

- Uneven load distribution  
- Network congestion  
- Inefficient power utilization  

The Optimal Power Flow (OPF) problem determines optimal operating conditions of a power system. However, traditional methods are:

- Centralized  
- Computationally expensive  
- Not scalable  

This project uses ADMM to enable distributed optimization based on:

**Distributed Optimal Power Flow Using ADMM – Tomaso Erseghe (IEEE, 2014)**

---

## ⚙️ Methodology  

### 🔹 Problem Formulation  

Minimize generation cost:
