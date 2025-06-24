
# Coupled Advection–Oscillation Simulation

This project simulates two coupled [partial differential equations](w) describing quantities **ω(x, t)** and **ε(x, t)**. The system models:

- **Advection** (transport) at speed `c`
- **Coupling** (local oscillation) at frequency `ϑ`:

  ∂ω/∂t + c ∂ω/∂x = ϑε

  ∂ε/∂t + c ∂ε/∂x = -ϑω


---

## Numerical Method

We split the problem into two steps:

1. **Advection** — solved using [`PyMPDATA`](w) for stable transport.
2. **Coupling (source terms)** — tested with:
   - **Explicit Euler** (unstable for oscillatory systems)
   - **Implicit Trapezoidal Rule** (used in the simulation for stability)

---

## Simulation Overview

- The initial ω bump moves right due to advection.
- Coupling causes energy exchange between ω (red) and ε (green).
- The trapezoidal scheme ensures stability and accuracy.

---

## Conclusion

- PyMPDATA handled advection effectively.
- The trapezoidal scheme proved stable and more accurate than Euler.
- The simulation captures the interaction of spatial transport and energy oscillation.
