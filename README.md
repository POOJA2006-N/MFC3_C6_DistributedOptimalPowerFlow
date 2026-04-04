# ⚡ Smart Grid Load Balancing using ADMM and MATPOWER

## 📄 Reference Paper
This project is based on:

**Distributed Optimal Power Flow Using ADMM**  
Tomaso Erseghe (IEEE, 2014)

---

## 🧠 Project Overview

This project implements a distributed optimization framework for solving the Optimal Power Flow (OPF) problem in smart grids using:

- ADMM (Alternating Direction Method of Multipliers)  
- MATPOWER (Power System Simulation Toolbox)  

The goal is to achieve scalable and efficient load balancing.

---

## 🚨 Problem Motivation

Modern power grids face:

- Increasing energy demand  
- Renewable energy integration  
- Network congestion  
- Uneven load distribution  

Traditional OPF methods are centralized and not scalable.

---

## 🎯 Objective

- Model load balancing as an optimization problem  
- Solve using ADMM  
- Use MATPOWER for simulation  
- Enable distributed computation  

---

## ⚙️ Mathematical Formulation

### Objective Function

Minimize total generation cost:

min Σ C_i(P_i), for all generators i ∈ G

---

### Power Flow Constraints

P_i = Σ V_i V_j (G_ij cosθ_ij + B_ij sinθ_ij)

---

### Power Balance Constraint

Σ P_generation = Σ P_demand

---

### Generator Limits

P_i(min) ≤ P_i ≤ P_i(max)

---

## 🔁 ADMM Formulation

We rewrite the optimization problem as:

min f(x) + g(z)

Subject to:

x = z

---

## 📐 Augmented Lagrangian

Lρ(x, z, λ) = f(x) + g(z) + λᵀ(x − z) + (ρ/2)‖x − z‖²

---

## 🔄 ADMM Iterations

### 1️⃣ x-update

x^(k+1) = argmin [ f(x) + (ρ/2)‖x − z^k + u^k‖² ]

---

### 2️⃣ z-update

z^(k+1) = argmin [ g(z) + (ρ/2)‖x^(k+1) − z + u^k‖² ]

---

### 3️⃣ Dual Update

u^(k+1) = u^k + x^(k+1) − z^(k+1)

---

## 🧪 Methodology

1. Load grid data using MATPOWER  
2. Extract bus and generator data  
3. Formulate OPF problem  
4. Apply ADMM decomposition  
5. Perform iterative updates  
6. Check convergence  

---

## 🔗 Role of MATPOWER

MATPOWER provides:

- Grid modeling (buses, generators, transmission lines)  
- Power flow computation  
- Optimal Power Flow (OPF)  

In this project:

- MATPOWER handles system physics  
- ADMM handles optimization  

---

## 📊 Results

- Balanced power distribution  
- Reduced generation cost  
- Scalable optimization  
- Distributed computation achieved  

---

## 📈 Comparison

| Aspect | Traditional OPF | ADMM-Based OPF |
|--------|----------------|----------------|
| Structure | Centralized | Distributed |
| Scalability | Low | High |
| Computation | Heavy | Parallel |
| Flexibility | Low | High |

---

## ⚠️ Challenges

- Parameter tuning (ρ)  
- Convergence issues  
- Non-convex nature of OPF  

---

## 🚀 Future Scope

- Renewable energy integration  
- Real-time smart grid systems  
- AI + ADMM hybrid optimization  
- Large-scale deployment  

---

## 🧾 Conclusion

This project demonstrates how ADMM-based distributed optimization enables:

- Efficient power distribution  
- Scalable smart grid operation  
- Practical implementation of OPF  

---
