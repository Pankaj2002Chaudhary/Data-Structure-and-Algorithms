# Vertex Cover Analysis using Brute Force, Greedy, and Maximal Matching

This project explores the **Vertex Cover problem** using multiple classical algorithms, 
analyzing their correctness, time complexity, advantages, and limitations.  
The Vertex Cover problem is a core NP-hard problem in graph theory, with applications 
in network security, bioinformatics, and social network analysis.

---

## 📌 Problem Definition

Given an undirected graph **G(V, E)**, a *vertex cover* is a set of vertices **C ⊆ V**  
such that **every edge in E has at least one endpoint in C**.

Goal:  
Find the *minimum vertex cover* — the smallest subset of vertices covering all edges.

Since the problem is NP-hard, we implement:

1. **Brute Force Search** (Exact)
2. **Greedy Heuristic**
3. **Maximal Matching Based 2-Approximation**

---

##  Algorithms Implemented

### 1️ **Brute Force Algorithm (Exact Solution)**  
- Enumerates all subsets of nodes  
- Checks which subsets form a valid vertex cover  
- Returns the smallest valid cover  

**Pros:**  
✔ Always finds the optimal solution  

**Cons:**  
✘ Exponential time → O(2ⁿ)  
✘ Works only for small graphs  

---

### 2️ **Greedy Vertex Cover (Heuristic)**  
Repeatedly selects the vertex with the highest degree, removes its incident edges, and continues.

**Pros:**  
✔ Fast  
✔ Easy to implement  

**Cons:**  
✘ No guarantee of optimality  
✘ Performance varies based on degree distribution  

---

### 3️ **Maximal Matching Based Algorithm (2-Approximation)**  
- Compute a *maximal matching* M  
- Vertex cover = all endpoints of matching edges  
- Guaranteed 2-approximation of optimal cover  

**Pros:**  
✔ Guaranteed approximation bound  
✔ Works well on large graphs  
✔ Polynomial time  

**Cons:**  
✘ May return a cover twice the optimal size  

---

##  Features of This Project

- Detailed implementation of all algorithms  
- Comparison of:
  - Running time  
  - Size of vertex cover  
  - Theoretical guarantees  
- Visual explanation using sample graphs  
- Performance charts for increasing graph sizes  

---

##  Example Usage

```python
from vertex_cover import brute_force_vertex_cover
from vertex_cover import greedy_vertex_cover
from vertex_cover import maximal_matching_vertex_cover

graph = {
    0: [1, 2],
    1: [0, 3],
    2: [0, 3],
    3: [1, 2]
}

print("Brute Force:", brute_force_vertex_cover(graph))
print("Greedy:", greedy_vertex_cover(graph))
print("Maximal Matching:", maximal_matching_vertex_cover(graph))
