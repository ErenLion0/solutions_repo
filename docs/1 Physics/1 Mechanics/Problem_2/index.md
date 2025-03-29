# Problem 2

---

title: "Forced Damped Pendulum"
-------------------------------

# 🌀 Investigating the Dynamics of a Forced Damped Pendulum

This webpage explores the motion of a special kind of pendulum: one that is affected by both **friction** and a **repeated pushing force**. This type of pendulum is called a **forced damped pendulum**.

You will learn:

- What the motion looks like,
- How to describe it with a mathematical equation,
- What happens when we change different parameters (like friction or the push),
- And how to simulate it using Python.

---

## 📚 What Is a Forced Damped Pendulum?

A normal pendulum swings back and forth because of gravity. But if you:

- **Add friction** (like air resistance),
- And **push it periodically** (like tapping it every second),

...then its motion becomes more interesting — and sometimes unpredictable. This system is called a **forced damped pendulum**.

To study it, we use a mathematical equation. The equation describes how the pendulum moves over time.

---

## 🧮 The Equation of Motion

The movement of the pendulum is described using this differential equation:

\[
\frac{d^2\theta}{dt^2} + b\frac{d\theta}{dt} + \frac{g}{L}\sin(\theta) = A\cos(\omega t
\]

Let’s break it down:

- \( \theta \) (theta) is the **angle** of the pendulum from the vertical (in radians).
- \( \frac{d^2\theta}{dt^2} \) is the **acceleration** (how fast the angle changes).
- \( \frac{d\theta}{dt} \) is the **angular velocity** (how fast it’s swinging).
- \( b \) is the **damping coefficient** – it controls how strong the friction is.
- \( g \) is the **gravitational acceleration** (about 9.81 m/s² on Earth).
- \( L \) is the **length of the pendulum**.
- \( A \) is the **amplitude of the external force** – how hard we are pushing it.
- \( \omega \) (omega) is the **frequency of the force** – how often we push it.
- \( \cos(\omega t) \) is the periodic push (a cosine wave).

---

## 🧠 Why Is This System Interesting?

This system behaves in **many different ways**, depending on the values of the parameters. Some key behaviors:

- If friction is strong, the pendulum slows down and stops.
- If you push it at the right frequency, it can swing **higher and higher** — this is called **resonance**.
- If the force is strong and damping is low, the motion can become **chaotic** — completely unpredictable and never repeating.

This is why scientists love this system: it’s simple to define, but the motion can become incredibly complex.

---

## 🧪 Simplifying the Equation

When the angle is **very small**, we can use this approximation:

\[
\sin(\theta) \approx \theta
\]

This turns the equation into a simpler, **linear** one:

\[
\frac{d^2\theta}{dt^2} + b\frac{d\theta}{dt} + \frac{g}{L}\theta = A\cos(\omega t)
\]

This version is easier to solve and helps us understand basic behaviors like resonance and damping.

---

## 💻 Simulating the Pendulum with Python

We can use a simple Python script to simulate how the pendulum moves. The code uses **Euler’s method**, a numerical technique to approximate the motion.

Below is the full code. It computes how the angle of the pendulum changes over time and saves the result as a plot.

```python
# Forced Damped Pendulum Simulation using Euler Method
import numpy as np
import matplotlib.pyplot as plt

# PARAMETERS
b = 0.5         # Damping (friction)
g = 9.81        # Gravity
L = 1.0         # Pendulum length
A = 1.2         # Driving force amplitude
omega = 2.0     # Driving force frequency

# INITIAL CONDITIONS
theta = 0.2     # Starting angle (radians)
v = 0.0         # Starting angular velocity
dt = 0.01       # Time step
T = 50          # Total simulation time
N = int(T/dt)   # Number of steps

# ARRAYS TO STORE DATA
t = np.linspace(0, T, N)
theta_list = []

# EULER METHOD LOOP
for i in range(N):
    a = -b*v - (g/L)*np.sin(theta) + A*np.cos(omega*t[i])  # Acceleration
    v += a*dt
    theta += v*dt
    theta_list.append(theta)

# PLOT THE RESULT
plt.plot(t, theta_list)
plt.xlabel("Time (s)")
plt.ylabel("Angle (radians)")
plt.title("Forced Damped Pendulum - Angle vs Time")
plt.grid()
plt.savefig("plots/theta_plot.png")
plt.show()
```
