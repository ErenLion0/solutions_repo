# Problem 2

# Forced Damped Pendulum


## Objective 

Study the behavior of a forced damped pendulum through theoretical analysis and numerical simulation. Examine its resonance, periodicity, and chaotic dynamics. Produce visualizations such as phase portraits, Poincaré sections, and bifurcation diagrams.

---

## Governing Equation

The forced damped pendulum is governed by the following nonlinear second-order differential equation:

d2θdt2+bdθdt+gLsin⁡θ=Acos⁡(ωt)\frac{d^2\theta}{dt^2} + b\frac{d\theta}{dt} + \frac{g}{L}\sin\theta = A\cos(\omega t)
Where:

* $\theta(t)$ is the angular displacement
* $b$ is the damping coefficient
* $g$ is gravitational acceleration
* $L$ is the length of the pendulum
* $A$ is the driving amplitude
* $\omega$ is the driving angular frequency

### Small-Angle Approximation

For small angles ($\theta \ll 1$), we can approximate:

sin⁡θ≈θ\sin\theta \approx \theta
The equation simplifies to:

d2θdt2+bdθdt+gLθ=Acos⁡(ωt)\frac{d^2\theta}{dt^2} + b\frac{d\theta}{dt} + \frac{g}{L}\theta = A\cos(\omega t)
This describes a linear damped driven oscillator.

---

## Natural Frequency and Resonance

The system's natural frequency under the small-angle approximation is:

ω0=gL\omega_0 = \sqrt{\frac{g}{L}}
Resonance occurs when $\omega \approx \omega_0$. At resonance, the pendulum oscillates with maximum amplitude. Damping reduces and broadens the resonance peak.

---

## Conversion to First-Order System

To solve the nonlinear equation numerically, we convert it into two first-order equations.

Define:

* $\theta_1 = \theta$
* $\theta_2 = \frac{d\theta}{dt}$

Then:

dθ1dt=θ2\frac{d\theta_1}{dt} = \theta_2
dθ2dt=−bθ2−gLsin⁡θ1+Acos⁡(ωt)\frac{d\theta_2}{dt} = -b\theta_2 - \frac{g}{L}\sin\theta_1 + A\cos(\omega t)
These equations are suitable for numerical integration.

---

## Parameter Effects

* **Damping ($b$)** : Controls energy loss. Larger $b$ leads to faster decay of oscillations.
* **Driving amplitude ($A$)** : Increases the system's energy. High $A$ may lead to chaos.
* **Driving frequency ($\omega$)** : Determines interaction with natural frequency.

---


### Poincaré Section

Sample the system at every period $T = \frac{2\pi}{\omega}$ and plot $\theta$ vs $\dot\theta$. Useful for identifying chaotic regimes.

```python
T_drive = 2 * np.pi / omega
poincare_t = np.arange(t_span[0], t_span[1], T_drive)
poincare_theta = np.interp(poincare_t, t, theta)
poincare_omega = np.interp(poincare_t, t, omega_vals)

plt.figure(figsize=(6, 6))
plt.scatter(poincare_theta, poincare_omega, s=1, color='red')
plt.title('Poincaré Section')
plt.xlabel('θ (rad)')
plt.ylabel('ω (rad/s)')
plt.grid()
plt.show()
```

### Bifurcation Diagram

Vary a parameter (e.g., $A$) and plot long-term values of $\theta$ at each period to observe transitions from periodic to chaotic motion.

```python
A_vals = np.linspace(0.5, 1.5, 200)
theta_ss = []

for A in A_vals:
    def pendulum_bif(t, y):
        theta, omega_dot = y
        dtheta_dt = omega_dot
        domega_dt = -b * omega_dot - (g / L) * np.sin(theta) + A * np.cos(omega * t)
        return [dtheta_dt, domega_dt]

    sol = solve_ivp(pendulum_bif, (0, 500), y0, t_eval=np.linspace(400, 500, 500), method='RK45')
    ss_theta = sol.y[0][::int(omega / (2 * np.pi) * 10)]
    for value in ss_theta:
        theta_ss.append((A, value))

A_plot, theta_plot = zip(*theta_ss)

plt.figure(figsize=(10, 6))
plt.plot(A_plot, theta_plot, ',', alpha=0.6)
plt.title('Bifurcation Diagram')
plt.xlabel('Driving Amplitude A')
plt.ylabel('θ (rad)')
plt.grid()
plt.show()
```


## Limitations

* Small-angle approximation only valid when $\theta \ll 1$
* Assumes rigid rod and point mass
* Ignores air resistance or external non-periodic disturbances

---

## Conclusion 

The forced damped pendulum demonstrates a rich set of behaviors, from simple oscillations to complex chaos. This code implements all required visualizations to explore those dynamics in line with theoretical expectations.

---

