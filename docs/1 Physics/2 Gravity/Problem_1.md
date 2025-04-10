# ** 📌Orbital Period and Orbital Radius**

## Motivation

The relationship between the square of the orbital period and the cube of the orbital radius, known as Kepler's Third Law, is a cornerstone of celestial mechanics. This simple yet profound relationship allows for the determination of planetary motions and has implications for understanding gravitational interactions on both local and cosmic scales. By analyzing this relationship, one can connect fundamental principles of gravity with real-world phenomena such as satellite orbits and planetary systems.

## Theoretical Background

### Kepler’s Third Law

> *The square of a planet’s orbital period is proportional to the cube of the semi-major axis of its orbit:*

\[
T^2 \propto r^3
\]

Where:

- \( T \): Orbital period
- \( r \): Orbital radius (assuming circular orbits)

### Newtonian Derivation

#### Equating Forces

Gravitational force equals the centripetal force for a circular orbit:

\[
\frac{G M m}{r^2} = \frac{m v^2}{r}
\]

Where:

- \( G \): Gravitational constant ≈ \( 6.674 \times 10^{-11} \, \text{m}^3/\text{kg} \cdot \text{s}^2 \)
- \( M \): Mass of the central body (e.g., Earth)
- \( m \): Mass of orbiting object
- \( v \): Orbital speed

#### Expressing Orbital Speed via Period

\[
v = \frac{2\pi r}{T}
\]

Substitute into the force equation:

\[
\frac{G M}{r^2} = \frac{(2 \pi r / T)^2}{r}
\]

Simplifying:

\[
T^2 = \frac{4 \pi^2 r^3}{G M}
\]

➡️ **Conclusion:** \( T^2 \propto r^3 \), confirming Kepler’s Law via Newtonian mechanics.

---

## 📊 Simulation: Orbital Period vs Radius

### Constants

```python
G = 6.67430e-11  # m^3 kg^-1 s^-2
M = 5.972e24     # kg (Earth's mass)

```

