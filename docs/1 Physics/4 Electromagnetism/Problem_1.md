# Simulating the effects of the Lorentz Force

## Motivation

The Lorentz force, expressed as $\mathbf{F} = q\mathbf{E} + q\mathbf{v} \times \mathbf{B}$, governs the motion of charged particles in electric and magnetic fields. It is foundational in fields like plasma physics, particle accelerators, and astrophysics. By focusing on simulations, we can explore the practical applications and visualize the complex trajectories that arise due to this force.

## 🔬 Theoretical Background

The motion of a charged particle in electric and magnetic fields is governed by the **Lorentz force**:

$$
\vec{F} = q\vec{E} + q\vec{v} \times \vec{B}
$$

Where:  
- $q$ is the electric charge of the particle,  
- $\vec{E}$ is the electric field vector,  
- $\vec{B}$ is the magnetic field vector,  
- $\vec{v}$ is the velocity of the particle.  

This expression combines two key phenomena:
1. **Electric force**: $q\vec{E}$ — accelerates the particle linearly in the direction of the field.
2. **Magnetic force**: $q\vec{v} \times \vec{B}$ — acts perpendicular to both the velocity and the magnetic field, causing circular or helical motion.

---

### 🧲 Magnetic Field Only

When $\vec{E} = 0$ and a uniform magnetic field $\vec{B}$ is present, the equation becomes:

$$
\vec{F} = q\vec{v} \times \vec{B}
$$

This results in **circular motion** of the charged particle in the plane perpendicular to $\vec{B}$. The radius of the circular path (Larmor radius) is:

$$
r = \frac{mv_\perp}{|q|B}
$$

And the angular frequency (cyclotron frequency) is:

$$
\omega = \frac{|q|B}{m}
$$

Where:  
- $v_\perp$ is the component of velocity perpendicular to $\vec{B}$,  
- $m$ is the mass of the particle.

If there’s a velocity component parallel to $\vec{B}$, the motion becomes **helical**.

---

### ⚡ Electric and Magnetic Fields (Crossed Fields)

When both $\vec{E}$ and $\vec{B}$ are nonzero and perpendicular to each other, the particle undergoes a **drift motion**. The drift velocity is given by:

$$
\vec{v}_d = \frac{\vec{E} \times \vec{B}}{B^2}
$$

This is known as the **$\vec{E} \times \vec{B}$ drift** and occurs regardless of the particle's charge or mass.

---

### 🧮 Equation of Motion

We simulate the system by numerically solving Newton's second law:

$$
m \frac{d\vec{v}}{dt} = q\vec{E} + q\vec{v} \times \vec{B}
$$

This results in a system of coupled differential equations that cannot be solved analytically in the general case, especially when $\vec{E}$ and $\vec{B}$ are functions of time or position. Therefore, we will use numerical integration methods to explore particle trajectories under various field configurations.

## 💻 Why Runge-Kutta Method?

The motion of a charged particle in electric and magnetic fields is governed by a system of coupled, nonlinear differential equations:

$$
m\frac{d\vec{v}}{dt} = q\vec{E} + q\vec{v} \times \vec{B}
$$

These equations are typically **not solvable analytically**, especially in the general case where $\vec{E}$ and $\vec{B}$ vary in space or time. Therefore, we must use **numerical integration techniques** to approximate the particle’s trajectory.

Among the available methods, the **Runge-Kutta 4th order (RK4)** algorithm offers a good balance between **accuracy** and **computational efficiency**. It reduces the local truncation error significantly compared to simpler methods like Euler's method.

The RK4 update steps for velocity $\vec{v}$ and position $\vec{r}$ are defined as:

- **Velocity update:**

$$
\vec{v}_{n+1} = \vec{v}_n + \frac{1}{6}(k_1^v + 2k_2^v + 2k_3^v + k_4^v)
$$

- **Position update:**

$$
\vec{r}_{n+1} = \vec{r}_n + \frac{1}{6}(k_1^r + 2k_2^r + 2k_3^r + k_4^r)
$$

Where:

$$
\begin{align*}
k_1^v &= a(\vec{v}_n)\Delta t \\
k_2^v &= a\left(\vec{v}_n + \frac{1}{2}k_1^v\right)\Delta t \\
k_3^v &= a\left(\vec{v}_n + \frac{1}{2}k_2^v\right)\Delta t \\
k_4^v &= a\left(\vec{v}_n + k_3^v\right)\Delta t \\
\\
k_i^r &= \text{corresponding velocity step} \times \Delta t
\end{align*}
$$

Here, $a(\vec{v})$ is the acceleration given by the Lorentz force:

$$
a(\vec{v}) = \frac{q}{m}(\vec{E} + \vec{v} \times \vec{B})
$$

This method allows us to simulate the particle’s motion with high temporal resolution, which is critical when studying fast-changing trajectories under Lorentz dynamics.

---

## 🔄 Simulation: Particle in Uniform Magnetic Field

We consider a charged particle with an initial velocity perpendicular to a uniform magnetic field $\vec{B} = B\hat{z}$. The electric field is zero: $\vec{E} = 0$.

The Lorentz force becomes:

$$
\vec{F} = q\vec{v} \times \vec{B}
$$

This results in circular motion in the $xy$-plane with constant speed.

- **Radius (Larmor Radius):**
  $$
  r = \frac{mv_\perp}{|q|B}
  $$

- **Cyclotron Frequency:**
  $$
  \omega = \frac{|q|B}{m}
  $$

- **Motion type:** Uniform circular motion.

---


![Charged Particle Motion in Uniform Magnetic Field](Charged_Particle_Motion_in_Uniform_Magnetic_Field.png)

---

> The particle moves in a perfect circle when its initial velocity is perpendicular to $\vec{B}$. No energy is gained or lost, and the speed remains constant.

---
## ⚡Crossed Electric and Magnetic Fields

We now consider a case where the electric and magnetic fields are perpendicular:

- $\vec{E} = [1, 0, 0]$
- $\vec{B} = [0, 0, 1]$

Initial velocity is set to $\vec{v}_0 = [0, 1, 0]$.

The Lorentz force becomes:

$$
\vec{F} = q(\vec{E} + \vec{v} \times \vec{B})
$$

This setup leads to a combination of **circular motion** due to the magnetic field and **linear drift** due to the cross product of the fields. The net drift velocity is given by:

$$
\vec{v}_d = \frac{\vec{E} \times \vec{B}}{B^2}
$$

For our configuration:

$$
\vec{v}_d = \frac{[1, 0, 0] \times [0, 0, 1]}{1^2} = [0, 1, 0]
$$

---

![Charged Particle Motion in Crossed Fields](Charged_Particle_Motion_in_Crossed_Fields.png)

---

> The charged particle exhibits a spiral trajectory in the $xy$-plane, superimposed with a constant drift in the $y$-direction. This is characteristic of $\vec{E} \times \vec{B}$ drift.
