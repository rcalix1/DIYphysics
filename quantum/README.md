## Quantum Computers

* https://www.youtube.com/watch?v=tHfGucHtLqo&t=31s
* https://www.youtube.com/watch?v=muoIG732fQA&t=24s
* 

---

# 🧪 DIY Quantum Projects

This README describes two foundational quantum experiments you can build and operate at home or in a small lab:

1. **Project 1: Bell Inequality Test Setup** — Create and measure entangled photon pairs to demonstrate a violation of Bell's inequality.
2. **Project 2: Photonic Quantum Logic Circuit** — Extend the Bell setup to implement a quantum logic gate (like CNOT) using entangled photons.

---

## 🔬 Project 1: DIY Bell Inequality Test Setup

### 🎯 Goal

Generate and detect entangled photon pairs using SPDC (Spontaneous Parametric Down-Conversion), then demonstrate a violation of the CHSH version of Bell's inequality.

[A](A.png)

### 🧠 What You'll Prove

* Entanglement is real and testable
* Local hidden variable theories cannot explain observed correlations
* You can violate Bell's inequality using simple optical tools

### 🔧 Components

| Component                                   | Description                             | Approx. Cost |
| ------------------------------------------- | --------------------------------------- | ------------ |
| **405 nm laser diode**                      | Safe violet laser (\~20–50 mW) for SPDC | \$20–50      |
| **BBO crystal (Type II)**                   | Nonlinear crystal for SPDC              | \$100–200    |
| **Optical breadboard and mounts**           | To align optics precisely               | \$100–200    |
| **Adjustable polarizers (2x)**              | For measurement basis selection         | \$50–100     |
| **Single-photon detectors (APDs or SiPMs)** | Detect entangled photons                | \$300–400    |
| **Coincidence counter**                     | Detect simultaneous events              | \$50–100     |
| **Safety goggles (405 nm OD3+)**            | Required for laser safety               | \$30–60      |

### 🧰 Setup Description

1. **Laser → BBO Crystal**: Collimated 405 nm beam enters the BBO crystal to produce pairs of 810 nm photons.
2. **Photon Collection**: Place irises and lenses to collect down-converted photons at \~3–5° angles.
3. **Measurement Stations**:

   * Each photon path has a polarizer and a detector.
   * Connect detectors to coincidence counter (e.g., DIY Arduino, or commercial unit).
4. **Data Collection**: Rotate polarizers to gather correlation statistics.
5. **Plot CHSH Expression**:
   $S = |E(a, b) + E(a, b') + E(a', b) - E(a', b')|$
   If $S > 2$, Bell’s inequality is violated.

### 📌 Notes

* Use very low optical powers and never look into beams.
* Use matte-black enclosures to suppress ambient light.
* Coincidence window timing must be in the nanosecond range.

---

## 🧠 Project 2: Photonic Quantum Logic Circuit

### 🎯 Goal

Build a photonic quantum gate (e.g., CNOT) using entangled photons. This demonstrates quantum logic acting on entangled states — the core of quantum computing.

### 🧠 What You'll Demonstrate

* Logic behavior on shared entangled states
* Quantum interference patterns
* Quantum logic without classical equivalents

### 🔧 Additional Components (on top of Project 1)

| Component                                  | Description                          | Approx. Cost |
| ------------------------------------------ | ------------------------------------ | ------------ |
| **Polarizing beam splitters (PBS, 2x)**    | Direct photons based on polarization | \$50–100     |
| **Waveplates (half-wave & quarter-wave)**  | Perform quantum logic rotations      | \$80–150     |
| **Additional mirrors & mounts**            | Create interference paths            | \$50–100     |
| **Optical delay lines (optional)**         | Match photon arrival time            | \$50–150     |
| **2 more detectors (for 4-channel logic)** | For logic gate output detection      | \$300–400    |

### 🧰 Setup Description

1. **Same SPDC Source**: Use your Bell setup’s entangled photon pair source.
2. **Logic Encoding**:

   * Assign |0⟩ and |1⟩ to horizontal and vertical polarizations.
   * Rotate with waveplates to set input states.
3. **Apply Logic (e.g., CNOT)**:

   * Use PBSs and waveplates to construct a CNOT or XOR logic operation.
   * Use post-selection: only record cases where photons are detected in certain correlated outputs.
4. **Measurement**:

   * Place detectors at output ports.
   * Use a coincidence counter to measure the logic result.
   * Compare actual logic truth table vs. observed result — matches only in quantum setup.

### 📌 Notes

* Single-photon logic relies on interference and proper photon indistinguishability.
* Small phase shifts can collapse the gate function — fine control is essential.

---

## 📎 Optional Enhancements

* Add a **Mach–Zehnder interferometer** to create quantum XOR gates.
* Use **delayed choice quantum eraser** modifications to show measurement-dependency of logic.
* Integrate with Python or Arduino for automated angle scanning and data plotting.

---

