<p align="center">
  <img src="logo.png" width="160"/>
</p>

<h1 align="center">
 ⚡ Distributed Optimal Power Flow  using ADMM 
</h1>
<p align="center">
  	22MAT220: Mathematics for Computing 3
</p>

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

This project uses distributed optimization based on:

**Distributed Optimal Power Flow Using ADMM – Tomaso Erseghe (IEEE, 2014)**

---

## ⚙️ Methodology  

### 🔹 Problem Formulation  

Minimize total generation cost:

![equation](https://latex.codecogs.com/png.image?\min\sum C_i(P_i))

Subject to:

**Power Balance Constraint:**  
Σ Pg = Σ Pd  

**Generator Limits:**  
Pi_min ≤ Pi ≤ Pi_max  

**Power Flow Equation:**  
Pi = Σ V_i V_j (G_ij cosθ + B_ij sinθ)  

---

### 🔹 ADMM Reformulation  

min f(x) + g(z)  
subject to x = z  

---

### 🔹 Augmented Lagrangian  

L(x,z,λ) = f(x) + g(z) + λᵀ(x − z) + (ρ/2)||x − z||²  

---

### 🔹 ADMM Updates  

**x-update:**  
$$x(k+1) = argmin f(x) + (ρ/2)||x − z + u||²  $$

**z-update:**  
z(k+1) = argmin g(z) + (ρ/2)||x − z + u||²  

**Dual update:**  
u(k+1) = u(k) + x(k+1) − z(k+1)  

---

### 🔹 Implementation Steps  

1. Load grid data using MATPOWER  
2. Extract bus and generator data  
3. Define cost functions and constraints  
4. Apply ADMM decomposition  
5. Perform iterative updates  
6. Check convergence  

---

## 📊 Dataset  

- IEEE standard bus systems (14-bus, 30-bus, etc.)  
- Available within MATPOWER  

👉 No external dataset required  

---

## 📈 Results  

### 🔹 Observations  

- Efficient load balancing achieved  
- Reduced generation cost  
- ADMM converges after iterations  

---

### 🔹 Graph  

![Convergence Graph](images/result.png)

**Fig 1:** ADMM convergence behavior over iterations  

---

### 🔹 Comparison  

| Method | Performance |
|------|------------|
| Centralized OPF | Accurate but not scalable |
| ADMM-Based OPF | Scalable and efficient |

---

## 🧾 Conclusion  

This project demonstrates that ADMM-based distributed optimization is an effective approach for solving large-scale smart grid load balancing problems. By combining MATPOWER for system modeling and ADMM for optimization, the system achieves scalable and efficient performance suitable for modern smart grids.

---

## 📁 Project Structure  
```
matpower-master/
admm_code/
data/
results/
images/
README.md
```


---

## 📚 References  

1. Distributed Optimal Power Flow Using ADMM – Tomaso Erseghe (IEEE, 2014)  
2. MATPOWER Documentation  
3. Boyd et al. – ADMM Optimization  
4. Power System Analysis textbooks  

---
