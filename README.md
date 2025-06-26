
<h1 style="color: purple; font-size: 64px;">Distributed Conflict Based Search (DCBS)</h1>

## 🧠 Brief Explanation

This project implements the **Distributed Conflict Based Search (DCBS)** algorithm, a **new** technique for solving the **Multi-Agent Path Finding (MAPF)** problem. The goal is to compute collision-free paths for multiple agents in a shared environment, such as robots navigating in a warehouse.

DCBS is a distributed version of the traditional Conflict Based Search (CBS) algorithm. It enables agents to independently plan their paths and coordinate via message passing to resolve conflicts, achieving scalability and near-optimal performance.

---
## 🙏 Acknowledgment

This project is inspired by the **Conflict-Based Search (CBS)** algorithm, a groundbreaking method for solving Multi-Agent Path Finding problems. We would like to express our deep appreciation to **Prof. Roni Stern**, who introduced CBS in collaboration with **Prof. Guni Sharon**, **Prof. Ariel Felner**, and **Prof. Nathan Sturtevant**.

Their foundational work has significantly shaped the field of cooperative pathfinding and served as the core motivation for our distributed variant.

---

## 📖 Citation 

If you use this project or base your research on it, please cite the original CBS work as follows:
-
Sharon, G., Stern, R., Felner, A., & Sturtevant, N. (2012). *Meta-agent conflict-based search for optimal multi-agent path finding*. In Proceedings of the International Symposium on Combinatorial Search (Vol. 3, No. 1, pp. 97–104).

## 🌍 Area

- Artificial Intelligence
- Distributed Systems
- Multi-Agent Coordination
- Path Planning

---

## 🧑‍💻 Code Language

- **Python 3.10+**

---

## 🚀 How to Run

1. **Prepare Map and Scenario Files**  
   Place maps and scenario files in the `Maps/<map_name>/` directory as required by the code (e.g., `random-32-32-10.map`, `scen-even/` directory).

2. **Run the Main Script**
   ```bash
   python main.py
   ```

3. **Output**
   - Console output with results per scenario and agent count.
   - CSV file saved under `results/` directory containing:
     - Grid name
     - Scenario number
     - Success (0 or 1)
     - Number of messages
     - Runtime (s)
     - Sum of cost
     - Number of agents

---

## 📊 Analytics

The experiment evaluates DCBS on multiple dimensions:

- **Runtime**: Total computation time for each scenario.
- **Message Count**: Total inter-agent messages exchanged.
- **Sum of Cost**: Total number of moves by all agents.
- **Success Rate**: Whether a conflict-free solution was found within a time limit.

### Experiment Parameters

- Maps: `random-32-32-10`, `empty-16-16`
- Agents: From 2 to 50
- Time limit per scenario: 5 minutes

---

## 📈 Results Summary

### Map: `random-32-32-10`

- DCBS performs optimally up to **36 agents**.
- Slight cost increase between **37–44 agents**.
- Solves up to **45 agents** within the time limit.
- **Runtime** slower than centralized CBS.

### Map: `empty-16-16`

- Optimal up to **20 agents**.
- Near-optimal for **21–24 agents**.
- Fails for >24 agents due to timeout.
- Message count and runtime increase with agent count.

---

## 🔬 Future Improvements

- Deepen the comparison between DCBS and CBS, focusing on A* behavior and identifying key differences.
- Test a strategy where only one agent starts the search to reduce duplicate nodes and message overhead.
- Enhance runtime using smarter conflict selection and A* optimizations, exploring other performance boosts.

---
