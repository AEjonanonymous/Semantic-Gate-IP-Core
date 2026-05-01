<h1 align="center">
Semantic + |Gate|✅|⛔|＝IP Core
</h1>

### Real-Time Manifold Integrity for Deterministic LLM Hallucination Suppression

[![License: AGPL v3](https://img.shields.io/badge/License-AGPL_v3-blue.svg)](https://opensource.org/licenses/AGPL-3.0) 
[![Hardware: SystemVerilog](https://img.shields.io/badge/Hardware-SystemVerilog-orange.svg)]()
[![Software: JavaScript](https://img.shields.io/badge/Software-JavaScript-yellow.svg)]()

**The Semantic Gate** is a hardware-accelerated monitor designed to bridge the **Semantic Gap** in Large Language Models. Unlike probabilistic software filters that rely on secondary referee AI models, this IP core enforces geometric constraints on embedding manifolds directly at the silicon level, providing a **Deterministic Killswitch** for hallucinations.

By moving from statistical guessing to **Manifold Integrity**, we provide a universal hardware root of trust for grounding AI outputs.

---

## ⚙️ How it Works
The core theory posits that valid logical transitions exist within a structured high-dimensional manifold. The Semantic Gate calculates the **Error Energy ($E$)** of an inference step using the **$L_{1}$ Norm (Manhattan Distance)**:

$$E=\sum_{i=1}^{VECTOR-DIM}|(\vec{A}_{i}+\vec{R}_{i})-\vec{V}_{i}|$$

**Example**: 

$$Vector(King) + Vector(Relation_{Gender}) \approx Vector(Queen)$$
* **PASS ✅**: Error Energy is low ($E < T$); the inference stays on the tracks of the high-dimensional surface.

**Example**: 

$$Vector(King) + Vector(Relation_{Gender}) \approx Vector(Toaster)$$
* **FAULT ❌**: Error Energy spikes ($E \gg T$); the output is geometrically disconnected, and the Semantic Gate triggers an immediate hardware killswitch.

The system includes a **Self-Calibration** state machine (WARMUP, CALIBRATION, ACTIVE) that learns the unique noise floor of any LLM to distinguish between acceptable model variance and genuine hallucinations.

---

## 📦 Deliverables & Package Structure
This repository contains a full-stack implementation for pre-silicon validation and high-throughput FPGA deployment.

### 📟 Hardware Layer (SystemVerilog RTL)
* `semantic_gate_pipelined_axi_core.sv`: The flagship IP core featuring a multi-stage pipelined accumulator and an integrated **AXI4-Stream Wrapper** to ensure high-speed processing without long combinational paths.
* `semantic_gate_pipelined_axi_core_testbench.sv`: Comprehensive verification environment used to validate accumulation logic against reference data.

### 💻 Software Layer
* `semantic_gate_engine.js`: A standalone Logic Engine that performs manifold mapping and geometric threshold analysis; serves as the functional source of truth for cross-layer hardware verification.
* `semantic_gate_testbench.html`: Web-based cross-validation tool for simulating the gate before hardware commitment.

### 🛠️ Tools
* `semantic_gate_vector_fabricator.html`: Tool used to generate fixed-point test vectors of variable size for verification.
* 🎁 **Bonus!** `Semantic Gate Prompt.pdf`: A customizable engineered prompt that approximates protocol behavior and manifold integrity for rapid testing within your preferred LLM environment.

### 📄 Documentation
* `The Semantic Gate - Real-Time Manifold Integrity for Deterministic LLM Hallucination Suppression.pdf`: Technical manuscript defining the Manifold Sparsity Hypothesis, Error Energy equations, and hardware-level deterministic killswitch logic.

---

## 📊 Proven Performance

The `semantic_gate_pipelined_axi_core.sv` was verified using `iverilog` to ensure cycle-accurate parity with the manifold math.

| Metric | Hardware Tier (Low-Dim) |
| :--- | :--- |
| **Vector Dimension** | 16 |
| **Total Cycles** | 100 |
| **Detections (Lies)** | 100/100 (100%) |
| **False Alarms** | 0/100 (0%) |
| **Status** | SUCCESS (Verified) |

**Technical Summary:**
* **Calibration**: The hardware successfully calculated a dynamic threshold ($T$) of **84256** based on the model's noise floor.
* **Performance**: The simulation reached `$finish` at **16097000 ps**, confirming the efficiency of the multi-stage pipelined accumulator.

The JavaScript engine was subjected to two distinct validation tiers to test both sensitivity and production-scale stability:

| Metric | Validation Tier (Low-Dim) | Production Tier (High-Dim) |
| :--- | :--- | :--- |
| **Vector Dimension** | 16 | **1536 (Industry Standard)** |
| **Detections (Lies)** | 100/100 (100%) | **1000/1000 (100%)** |
| **False Alarms** | 5/100 (5%) | **0/1000 (0%)** |
| **Status** | SUCCESS | **SUCCESS (High Precision)** |

**The Manifold Sparsity Hypothesis:** As dimensionality increases to industry standards ($DIM=1536$), the gap between grounded logic and hallucinations increases exponentially, allowing for a deterministic killswitch without sacrificing system availability.

---

## 💼 Commercial Applications
* **Hyperscale Cloud Infrastructure ☁️**: Replace expensive, high-latency software filters with a low-power, sub-microsecond hardware firewall.
* **Clinical & Medical AI 🏥**: Ensure generated dosages or chemical compounds never deviate from an established medical truth manifold, providing a path toward regulatory certification.
* **Autonomous Systems & Aerospace 🤖**: Act as a physical Manhattan fence to intercept and kill hallucinated commands before they result in catastrophic physical actions.
* **Legal, Financial & Sovereign Data 🏛️**: Generate an immutable log of Error Energy to prove an AI remained grounded in specific context or case law during a session.

---

## ⚖️ Licensing & Usage
**The Semantic Gate IP Core** is available under a dual-licensing model to balance community innovation with high-performance industrial needs.

* **Open Source (AGPL-3.0)**: Ideal for public research, open-source infrastructure, and community-driven projects. This license requires that any derivative works or network-hosted versions of the protocol remain open-source.
* **Commercial License**: Required for closed-source applications, proprietary hardware synthesis (**ASIC/FPGA**), or integration into private enterprise platforms. This license provides an exemption from the AGPL copyleft requirements.

For commercial licensing inquiries, please contact:
**Licensing Agent** - J.E. Randolph 📧 [700josh.r@gmail.com](mailto:700josh.r@gmail.com)
