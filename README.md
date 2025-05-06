# **NuSMV Bit-Shifter Finite State Machine (FSM) - Formal Verification Model**  

![NuSMV](https://img.shields.io/badge/NuSMV-2.7.0-blue)  
![Formal Verification](https://img.shields.io/badge/Formal_Verification-LTL-green)  
![License](https://img.shields.io/badge/License-MIT-orange)  

## **📌 Overview**  
This repository contains a **formally verified Finite State Machine (FSM)** model implemented in **NuSMV**, a symbolic model checker for hardware and software verification. The model demonstrates:  
✅ **2-bit shifter logic** with states `{a, B, C, D}`  
✅ **Input-driven transitions** with Boolean outputs (`Bit1`, `Bit2`)  
✅ **Linear Temporal Logic (LTL)** specifications for correctness guarantees  
✅ **Deadlock-free & reachability-verified** design  

Designed for **researchers, engineers, and students** in formal methods, this project serves as a **reference implementation** for:  
- **FSM modeling in NuSMV**  
- **LTL specification writing**  
- **Formal verification best practices**  

---

## **🚀 Key Features**  
✔ **Complete State Transitions** – Covers all `input` cases (TRUE/FALSE)  
✔ **Deterministic Output Logic** – `Bit1` mirrors input, `Bit2` state-dependent  
✔ **4 LTL Specifications** – Verifies:  
   - `G(Bit1 → X Bit2)` (Bit correlation)  
   - `G(Bit1 → X Bit1)` (Latching behavior)  
   - `G(F state = D)` (Reachability)  
   - Deadlock freedom  
✔ **Production-Ready Code** – Robust fallbacks, no syntax errors  

---

## **📂 Repository Structure**  
```plaintext
nusmv-bit-shifter-fsm/  
├── models/  
│   └── bit_shifter_fsm.smv       # Main NuSMV model  
├── docs/  
│   ├── fsm_diagram.png           # State transition graph  
│   └── specifications.md         # LTL spec explanations  
├── scripts/  
│   └── run_verification.sh       # NuSMV automation script  
├── LICENSE                       # MIT License  
└── README.md                     # This file  
```

---

## **🔧 How to Run**  
### **Prerequisites**  
- Install [NuSMV 2.7+](http://nusmv.fbk.eu)  

### **Verification Steps**  
1. Clone the repository:  
   ```bash
   git clone https://github.com/sardaralikhamosh/nusmv-bit-shifter-fsm.git
   cd nusmv-bit-shifter-fsm
   ```  
2. Run verification:  
   ```bash
   NuSMV models/bit_shifter_fsm.smv
   ```  
3. Expected output:  
   ```plaintext
   -- Specification G(Bit1 -> X Bit2) is true
   -- Specification G(Bit1 -> X Bit1) is true
   ...  
   ```  

---

## **📊 State Transition Diagram**  
![FSM Diagram](https://github.com/sardaralikhamosh/formal-verification-fsm/blob/main/fms-diagram.jpg) 
*(Generated with Graphviz – see [docs/](docs/) for source.)*  

| State | Input | Next State |  
|-------|-------|------------|  
| **a** | TRUE  | B          |  
| **a** | FALSE | a          |  
| **B** | TRUE  | D          |  
| **B** | FALSE | C          |  
| ...   | ...   | ...        |  

---

## **📜 LTL Specifications Explained**  
| Specification | Meaning |  
|--------------|---------|  
| `G(Bit1 → X Bit2)` | "If Bit1 is TRUE, Bit2 must be TRUE in the next step" |  
| `G(Bit1 → X Bit1)` | "Bit1 remains TRUE once set (non-stuttering)" |  
| `F state = D` | "State D is eventually reachable" |  

See [docs/specifications.md](docs/specifications.md) for details.  

---

## **📝 License**  
This project is licensed under the **MIT License**. See [LICENSE](LICENSE).  

---

## **💡 Use Cases**  
- **Teaching FSM verification** in formal methods courses  
- **Benchmarking** NuSMV performance  
- **Template** for hardware control logic verification  

---

## **Author**  
[Sardar Ali Khamosh](https://github.com/sardaralikhamosh)

[Web Profile](http://shinisa.com/sardaralikhamosh)

[LinkedIn](https://pk.linkedin.com/in/sardaralikhamosh)

---

## **🔍 Keywords**  
`NuSMV tutorial`, `formal verification FSM`, `LTL model checking`, `finite state machine example`, `bit shifter verification`, `NuSMV best practices`, `symbolic model checker`, `deadlock-free design`  

---
