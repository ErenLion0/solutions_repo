# Trajectories of a Freely Released Payload Near Earth

## Motivation:
When an object is released from a moving rocket near Earth, its trajectory depends on initial conditions and gravitational forces. This scenario presents a rich problem, blending principles of orbital mechanics and numerical methods. Understanding the potential trajectories is vital for space missions, such as deploying payloads or returning objects to Earth.

## 📚 Theoretical Foundation

The motion of a payload released near Earth is governed by Newton’s Law of Universal Gravitation and classical mechanics. The gravitational force acting on the payload is:

$$
\vec{F}_g = -\frac{GM_{\text{Earth}}m}{r^2} \hat{r}
$$

This results in an acceleration toward the Earth’s center, influencing the trajectory based on initial speed and direction.

---

## 💻 Why Runge-Kutta Method?

The motion of the payload is governed by a system of differential equations derived from Newton’s second law. Since an analytical solution is generally not possible for these nonlinear, multidimensional systems, we use a numerical solver.

The Runge-Kutta (4th order) method provides a robust and accurate way to simulate the trajectory over time. It balances stability and computational efficiency, making it ideal for solving orbital dynamics problems.

---

## 🧮 Total Mechanical Energy of the System

The total energy $( E )$ of a payload of mass $( m )$, located at distance $( r )$ from the Earth's center and moving at speed $( v )$, is:

$$
E = \frac{1}{2}mv^2 - \frac{GM_{\text{Earth}}m}{r}
$$

The type of orbit depends on the **sign of the total mechanical energy**:

- **Elliptical Orbit**: $( E < 0 )$ → Bound orbit (sub-orbital or closed elliptical)
- **Parabolic Trajectory**: $( E = 0 )$ → Exactly at escape velocity
- **Hyperbolic Trajectory**: $( E > 0 )$ → Exceeds escape velocity, escapes Earth

---

## 🔁 Orbit Classification Summary

| Energy $( E ) $           | Speed Range            | Trajectory Type     | Description                             |
|---------------------------|------------------------|---------------------|------------------------------------------|
| $( E < 0 )$               | $( v < v_{\text{escape}} )$ | Elliptical          | Closed orbit, object remains around Earth |
| $( E = 0 )$               | $( v = v_{\text{escape}} )$ | Parabolic           | Escape trajectory, marginal case         |
| $( E > 0 )$               | $( v > v_{\text{escape}} ) $| Hyperbolic          | Object escapes Earth permanently         |

---

## 🌍 Initial Conditions for the Simulation

For this study, the payload is released from a position:

- **800 km above Earth's surface** → $( r_0 = R_{\text{Earth}} + 800 \times 10^3 \ \mathrm{m} )$
- **Initial velocity is tangential**, and varied from **5 km/s to 13 km/s**

These values will be used in our numerical simulation to classify the resulting paths and visualize the orbital behavior.

- [Colab Link](https://colab.research.google.com/drive/1d4qakItrgnRNwwB_QKfUjb9UJ27hIiml#scrollTo=CF7ICmaoA3O4)

![Payload Trajectories in Earth's Gravitational Field](<Payload_Trajectories_in Earths_Gravitational_Field.png>)

## 🛰️ Payload Trajectories from 800 km Altitude

This simulation illustrates how different initial tangential velocities determine the path of a freely released payload in Earth's gravity field. Starting 800 km above Earth's surface, the payload is given initial speeds ranging from **5.0 km/s to 13.0 km/s**.

**Key Observations:**

- **Below 7.5 km/s**: Suborbital motion — payload eventually crashes back to Earth.
- **7.5–10.0 km/s**: Stable elliptical orbits — possible satellite deployment speeds.
- **~11.2 km/s**: Parabolic escape — threshold velocity for leaving Earth’s gravity.
- **Above 11.2 km/s**: Hyperbolic escape — spacecraft escapes Earth with excess velocity.

Each trajectory was simulated numerically under Newtonian gravity. The Earth is modeled as a circle, and initial conditions are consistent across all runs except tangential speed.

# 📌 Real-World Application Relevance
- **Orbital Insertion:**
 
  Speeds around 7.8 km/s are used to achieve low Earth orbit.

- **Reentry Dynamics:**

  Suborbital speeds simulate missile-like descent or capsule return.

- **Escape Scenarios:**
 
  Speeds beyond 11.2 km/s represent interplanetary missions.

 - **Space Mission Planning:**  
  Accurate trajectory analysis ensures mission success by optimizing launch parameters, transfer orbits, and fuel efficiency.

 - **Satellite Deployment:**  
  Depending on the satellite’s target orbit (LEO, MEO, GEO), the required insertion velocity and trajectory vary significantly.

 - **Planetary Exploration:**  
  Missions to the Moon, Mars, or beyond require understanding escape conditions and interplanetary transfer paths.  
  Simulating these trajectories helps design gravity assists and deep space navigation.

This foundational analysis supports practical space operations and exploration strategies.

---

## 🔍 Discussion: Relevance to Spaceflight and Mission Design

The simulation clearly demonstrates how a payload’s initial tangential speed determines its orbital behavior when released near Earth:

- **Suborbital trajectories** $(v < 7.5 km/s)$ correspond to failed orbital insertions or intentional reentry profiles — similar to early test flights and ballistic missiles.
- **Elliptical orbits** $(v ≈ 7.5–10.0 km/s)$ are used in many satellite deployments, space station logistics, and planetary capture phases.
- **Parabolic escape** $(v ≈ 11.2 km/s)$ represents the threshold velocity for leaving Earth's gravitational influence — critical for planning interplanetary transfer windows.
- **Hyperbolic escape** $(v > 11.2 km/s)$ models high-speed deep-space missions, such as Voyager and New Horizons, and concepts for interstellar probes.

By simulating these trajectories, engineers can determine optimal launch speeds, fuel budgets, and mission viability based on gravitational constraints. This analysis is also key to understanding spacecraft reentry windows, orbit maintenance, and planetary arrival timing.

---

## ✅ Conclusion

In this project, we analyzed how a payload released from 800 km altitude behaves under different tangential speeds using Newtonian mechanics and gravitational dynamics.

- We derived the governing forces and energy relationships.
- We classified trajectories based on mechanical energy: elliptical, parabolic, and hyperbolic.
- Using Python simulations, we visualized the resulting motion paths from 5.0 km/s to 13.0 km/s.
- We compared these outcomes to real-world mission categories such as orbital insertion and escape.

This project not only reinforces gravitational theory but also highlights its direct application to modern space exploration and mission planning. Through simulation and analysis, we better understand how initial conditions shape a spacecraft’s entire journey.
