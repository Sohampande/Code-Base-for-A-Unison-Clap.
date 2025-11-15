# The Mathematics of a Unison Clap  
*A Monte Carlo Simulation of Emergent Synchrony in Crowds*

---

###  Run the Simulation Yourself

If you want to try the unison clap experiment on your own machine, you can clone my GitHub repository and run the notebook or script.

```bash
git clone https://github.com/<Sohampande>/Audience-Clap-CLT.git
cd Audience-Clap-CLT
python unison_clap_simulation.py
```

Alternatively, if you're using the Jupyter notebook:

```bash
jupyter notebook "The Unison Clap.ipynb"
```
---

## Overview

Have you ever noticed that during concerts, even when every audience member claps at slightly different times, it somehow sounds like **one big synchronized clap**?
This repository simulates that phenomenon using **NumPy**, **pandas**, and **Matplotlib**, and shows that what sounds like perfect synchronization is actually a beautiful example of the **Central Limit Theorem (CLT)** in action.
By modeling each clap as a short decaying waveform with random timing jitter and amplitude variation, we demonstrate how **averaging over many random events produces order from chaos**.

---

## Project Goals

- Simulate audience claps with realistic micro-timing variations.
- Use Monte Carlo methods to visualize how random claps converge to a unified waveform.
- Demonstrate **LLN (Law of Large Numbers)** and **CLT (Central Limit Theorem)** scaling behavior.
- Explain mathematically and visually why large groups sound “in sync.”

---

## Key Concepts

| Concept                         | Description                                                                                    |
|---------------------------------|------------------------------------------------------------------------------------------------|
| **Law of Large Numbers (LLN)**  | As we average more random signals, the mean approaches a stable expected value.                |
| **Central Limit Theorem (CLT)** | Variability around the mean decreases as \(1/\sqrt{N}\), producing smoother, unified patterns. |
| **Emergent Synchrony**          | Apparent synchronization that arises from statistical averaging of random individual actions.  |

---

## Simulation Structure

The project follows five stages, matching the structure in the code:

1. **Parameter Setup**  
   Define the sampling rate, clap waveform, and jitter kernel.

2. **Waveform Model**  
   Each clap is modeled as an exponentially decaying signal:  
   \[
   s(t) = e^{-t/\tau}
   \]

3. **Audience Simulation**  
   Generate \(N\) random clappers, each with:
   - A random time delay (Gaussian jitter)
   - A random amplitude (lognormal distribution)
   - The waveform \( s(t - \tau_i) \)

4. **Monte Carlo Trials**  
   Repeat the simulation for many runs to estimate:
   - Mean waveform shape
   - Peak amplitude distribution
   - Coefficient of variation (CV) scaling

5. **Visualization**  
   - Plot mean waveforms vs. the theoretical mean \( N \cdot m(t) \)  
   - Plot the CV vs. \(N\) on a log–log scale to confirm CLT scaling (\( \propto N^{-1/2} \))

---

## 📈 Example Results

| Plot                         | Interpretation                                                                                    |
|------------------------------|---------------------------------------------------------------------------------------------------|
| **Mean Waveforms vs Theory** | As audience size increases, the waveform becomes smoother and approaches the theoretical average. |
| **CV Scaling (log–log)**     | Confirms CLT prediction — variability decreases proportionally to \(1/\sqrt{N}\).                 |


---

## Dependencies

This project uses standard scientific Python libraries:

```bash
pip install numpy pandas matplotlib
```
git clone https://github.com/<your-username>/Audience-Clap-CLT.git
cd Audience-Clap-CLT
python unison_clap_simulation.py
```
