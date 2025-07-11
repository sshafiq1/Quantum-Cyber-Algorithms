# Assessing Trade-Offs in Utilising BB84 vs B92 for Quantum Key Distribution

### Team members: Rose Zhao, Sarah Shafiq, Hanvitha Kunkalaguntla

## Description:
This research project investigates the security and performance trade-offs between two foundational quantum key distribution (QKD) protocols: BB84 and B92. While B92 offers simplified implementation by using only two non-orthogonal polarization states, BB84—leveraging two mutually unbiased bases—is considered the gold standard due to its stronger security against eavesdropping attacks.

To quantify these differences,  We are developing a Monte Carlo simulation in Python that models intercept-resend attacks and evaluates key rate and error thresholds. This includes exploring advanced quantum information concepts such as the Breidbart basis, minimum-error discrimination, and the Helstrom bound. Through this work, we aim to numerically demonstrate BB84’s superior security margin over B92 while also identifying scenarios where B92 may be practically advantageous due to cost or implementation constraints.

The project integrates quantum theory with statistical simulation and visualization, requiring fluency in QKD protocols, attack models, and Monte Carlo methods.

### Key Skills:
Quantum Cryptography · Python · Monte Carlo Simulation · Data Visualization · Information Security · Quantum Algorithms

### Notebook Breakdown:

**Ideal Case**
- Simulate BB84 protocol without any noise or eavesdropping.
- **Metrics used**:
  - `Raw key length`
  - `Sifted key length`
  - `Key retention rate` (sifted/raw)
  - `Quantum Bit Error Rate (QBER)` — expected to be near 0%
  - `Expected error rate`: 0.0 (baseline)

---

**Noise Case**
- **Noise models used**:
  - Bit flip
  - Phase flip
  - Depolarizing noise
  - Amplitude damping
- **Metrics used**:
  - `QBER` (expected to increase under noise)
  - `Key retention rate`
  - `Error rate deviation` from ideal
  - `Statistical detection` of abnormal error rates

---

**Eavesdropping Case**
- **Eavesdropping models used**:
  - Intercept-resend attack
  - Breidbart basis attack
  - Variable interception probability and basis strategies
- **Metrics used**:
  - `QBER`
  - `Eve detection statistics`:
    - `Eve detected` (boolean)
    - `Detection confidence`
    - `P-value` (from binomial test)
  - `Intercepted fraction` (of sifted bits)
  - `Security breach rate` (QBER > threshold, e.g., 11%)
  - **Attack effectiveness**:
    - `Information gain` (from Eve)
    - `Stealth score` = 1 − detection rate
    - `Disturbance score` = QBER
