# Lorentz Simulator

*A single‑file, client‑side visualizer for special relativity: Lorentz boosts, time dilation, velocity composition, and a Minkowski diagram.*

> **Live demo (GitHub Pages):** `https://<your-username>.github.io/lorentz-simulator/`\
> **Repo:** `https://github.com/<your-username>/lorentz-simulator`

---

## Why this simulator? (Purpose)

Understanding **special relativity** is easiest when you can *see* how spacetime coordinates transform. This simulator provides:

- **Immediate intuition** for how events move between frames under a Lorentz boost.
- **Hands-on experiments** with **time dilation**, **relativity of simultaneity**, and **velocity addition**.
- A clean **Minkowski diagram** showing light cones, the boosted axes, worldlines, and your chosen event.

Use it for self‑study, classroom demos, or quick checks while writing/teaching physics.

---

## What it does (Features)

- **Lorentz boost calculator** (1D):
  - Inputs: invariant speed `c`, boost speed `v` (as a fraction of `c`), event \((t,x)\), optional particle speed `u` (as a fraction of `c`), and diagram window `T`.
  - Outputs: \(\beta = v/c\), \(\gamma = 1/\sqrt{1-\beta^2}\), transformed event \((x',t')\), proper time \(\Delta\tau\), velocity composition \(u\oplus v\), and velocity seen in the primed frame \(u'\).
- **Minkowski diagram** (ct vs x):
  - **Light cone** lines \(x = \pm ct\).
  - **Worldline of S′ origin**: \(x = v t\).
  - **x′ axis** (\(t' = 0\)) line: \(ct = (v/c)\,x\).
  - **Event marker** at \((x, ct)\) with subtle shading for **timelike / spacelike / lightlike** classification via \(s^2 = c^2 t^2 - x^2\).
- **Natural units toggle**: set \(c = 1\) to simplify thinking.
- **Export**: one‑click **Download PNG** of the diagram.
- **Privacy & portability**: 100% client‑side; hostable as a single `index.html` on GitHub Pages.

---

## How to use

1. \*\*Set \*\*\`\` (defaults to the SI value) or toggle **Use natural units**.
2. Choose a \*\*boost speed \*\*\`\` as a fraction of `c` (slider or number).
3. Enter an **event**: time `t` (s) and position `x` (m).
4. Optionally set a \*\*particle speed \*\*\`\` (fraction of `c`) to explore composition and velocity transform.
5. Adjust the \*\*time window \*\*\`\` (s) to zoom the diagram. The x‑range is automatically ±`cT`.
6. Hit **Compute transforms**. The stats panel updates; the diagram redraws.

**Outputs explained:**

- **β**: dimensionless speed, \(\beta = v/c\).
- **γ**: time dilation/length contraction factor, \(\gamma = 1/\sqrt{1-\beta^2}\).
- **(x′, t′)**: the event’s coordinates in the boosted frame S′.
- **Δτ**: proper time tick for a moving clock relative to coordinate time \(\Delta t\).
- **u ⊕ v**: relativistic addition of velocities measured in the same frame (saturates below \(c\)).
- **u′**: the velocity measured in S′ for an object moving at `u` in S.

---

## Equations used

All along one spatial dimension (boost along x):

- **Lorentz boost**

  - \(x' = \gamma (x - v t)\)
  - \(t' = \gamma \Bigl(t - \dfrac{v x}{c^2}\Bigr)\)
  - \(\gamma = \dfrac{1}{\sqrt{1 - v^2/c^2}}\), \(\beta = v/c\)

- **Velocity composition** (same-frame composition):

  - \(u \oplus v = \dfrac{u + v}{1 + \dfrac{uv}{c^2}}\)

- **Velocity transform** (speed `u` in S seen from S′):

  - \(u' = \dfrac{u - v}{1 - \dfrac{uv}{c^2}}\)

- **Interval classification**:

  - \(s^2 = c^2 t^2 - x^2\) ⇒ timelike (\(s^2>0\)), spacelike (\(s^2<0\)), lightlike (\(s^2=0\)).

---

## Try these quick experiments

- **Time dilation**: Set `x=0` and increase `|v|`. Observe \(\Delta\tau = \Delta t\sqrt{1-\beta^2}\) shrinking relative to \(\Delta t\).
- **Relativity of simultaneity**: Look at the dashed **x′ axis** (\(t'=0\)). Its slope \(ct = (v/c) x\) shows “simultaneous” in S′ is *tilted* in S.
- **Velocity caps**: Push `u` and `v` near `c` and check **u ⊕ v**—it never exceeds `c`.
- **Intervals**: Move `x` and `t`. Watch the shaded background label switch between **timelike / spacelike / lightlike** as \(s^2\) changes sign.

---


