# Network Deployment Optimizer

This project applies Mixed Integer Linear Programming (MILP) to optimize the deployment of wireless cellular networks. It explores and compares macro-only, micro-only, and mixed base station configurations over a 1500m × 1500m area using realistic radio propagation and throughput models.

---

## Project Overview

- **Optimization Objective**: Minimize total deployment cost while ensuring full coverage and required throughput.
- **Technology**: MILP (via Python), Okumura-Hata path loss model, Shannon capacity theorem.
- **Deployment Types**: Macro, Micro, and Mixed base stations.

---

## Mathematical Model

### Sets
- `C`: Candidate Sites (50)
- `T`: Test Points (100)
- `B`: Base Station Types = {macro, micro}

### Parameters
- `cost[c,b]`: Installation cost
- `coverage[c,t,b]`: Binary (0/1) signal coverage
- `throughput[c,t,b]`: Estimated Mbps throughput
- `min_thr`: Minimum throughput = 7 Mbps

### Decision Variables
- `install[c,b]`: Whether to install BS type `b` at site `c`
- `serve[c,t,b]`: Whether BS at `c` serves test point `t`

### Objective
Minimize total cost across selected deployments and assignments.

---

## Simulation Results

| Scenario     | Total Cost | Macro BS | Micro BS | Deployed Sites              |
|--------------|------------|-----------|-----------|-----------------------------|
| Macro-only   | $9.24      | 4         | 0         | [24, 26, 39, 42]            |
| Micro-only   | $7.32      | 0         | 12        | [4, 6, 10, ..., 48]         |
| Mixed        | $6.77      | 1         | 9         | Macro: [26], Micro: [1,...] |

- 100% coverage in all scenarios
- All test points meet throughput requirement
- Mixed scenario achieves lowest cost with balanced performance

---

## 📈 Visualizations

- Coverage maps for each scenario
- Throughput and cost comparison charts
- Network topologies for deployment strategies

---

## How to Run

You can view and run the project on Google Colab:

[Open Notebook](https://colab.research.google.com/drive/12T0WBu_Vr4ub91-DC5ij-ran_-aIZMRD#scrollTo=UM9yRCNScmTL)
