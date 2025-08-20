# Project 1: Quantum Entanglement Core

## 🧠 Description

This project combines two powerful quantum experiments into a single modular setup:

* **Bell Inequality Verification** to prove real entanglement (https://github.com/rcalix1/DIYphysics/tree/main/quantum).
* **Photonic CNOT Gate** to demonstrate basic quantum logic.

Together, they form a real, functioning entanglement core that is not only educational but foundational for exploring advanced quantum devices.

---

## 🔬 Scientific Basis

* **Bell’s Theorem** proves that entangled particles show correlations that can’t be explained by classical physics or local hidden variables.
* **Spontaneous Parametric Down-Conversion (SPDC)** in a nonlinear crystal (e.g. BBO) produces entangled photon pairs.
* **Photonic Logic Gates** (e.g. CNOT) manipulate and test entangled quantum states using beam splitters, polarizers, and interference.

---

## 🎯 Project Goals

* Build a DIY setup to generate and detect entangled photons.
* Perform the Bell Inequality experiment and log results.
* Construct a basic quantum logic gate to manipulate entangled photons.

---

## 🧩 Modules / Components

1. **Laser Source**

   * Type: 405nm diode laser, Class IIIa (safe with protection)
2. **Nonlinear Crystal**

   * Type: BBO (Beta-Barium Borate), cut for type I or II SPDC
3. **Beam Splitters**

   * Non-polarizing and polarizing varieties (PBS)
4. **Polarizers / Waveplates**

   * Rotatable linear polarizers and half-wave plates
5. **Photon Detectors**

   * Silicon avalanche photodiodes (APDs) or photomultiplier tubes
6. **Coincidence Logic / Counter**

   * For detecting correlated events from entangled photons
7. **Optical Mounts / Rails**

   * Precision alignment tools
8. **CNOT Gate (Optional)**

   * Built using beam interference, PBS, and projective measurement

---

## 🛠️ Build Instructions (High-Level)

1. **Align the laser into the BBO crystal** to create SPDC photon pairs.
2. **Place polarizers and waveplates** to test correlations.
3. **Use beam splitters and detectors** to measure photon states.
4. **Log results to test Bell's Inequality** using CHSH formula.
5. **Extend to a basic CNOT** logic operation with photon interference.

---

## 📊 Experimental Procedure

* Measure photon polarizations at multiple angles.
* Record detection coincidences for each pair of angles.
* Calculate the Bell parameter $S$ using the **CHSH inequality**:

$S = |E(a, b) - E(a, b') + E(a', b) + E(a', b')|$

Where $E(a, b)$ is the correlation function between measurement settings $a$ and $b$.

* In classical systems, $|S| \leq 2$. Quantum entanglement can reach up to $|S| = 2\sqrt{2} \approx 2.828$.

### Example Experimental Results

* At angle settings $a = 0^\circ, a' = 45^\circ, b = 22.5^\circ, b' = 67.5^\circ$:

  * Calculated $S \approx 2.62$
  * Clear violation of Bell’s inequality, confirming quantum entanglement

---

## 👁️ Results / Observables

* Coincidence spike at entangled angles.
* Violation of Bell’s inequality (e.g., $S \approx 2.6$).
* Interference pattern changes based on gate logic.

---

## ⚠️ Risks & Safety

* Use **laser safety goggles** at all times.
* Use enclosures to block stray beams.
* Handle detectors and electronics with care.

---

## 🔄 Future Extensions

* Integrate with **Entanglement Radio** as a signal source.
* Add more logic gates for full quantum computation.
* Use faster logic for real-time entanglement-based control.

---

## 🧵 References

* Alain Aspect, Zeilinger et al. — Experimental Tests of Bell’s Inequality
* Qiskit tutorials on quantum logic gates
* DIY entanglement experiments: many open-source optics guides available


