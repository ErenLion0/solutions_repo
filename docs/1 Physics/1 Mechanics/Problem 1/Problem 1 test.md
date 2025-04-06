# 📌 **Investigating the Range as a Function of the Angle of Projection**

## **Problem Statement**

The goal of this experiment is to analyze the relationship between the **launch angle ($\theta$)** and the **horizontal range ($R$)** of a projectile.

---

## **Theoretical Background**

### Newton's Second Law

To analyze projectile motion, we begin with Newton’s Second Law of Motion:

$$
\vec{F} = m \vec{a}
$$

This law states that the net force acting on an object is equal to its mass multiplied by its acceleration. We apply this principle separately to the horizontal and vertical components of motion.

### 1. Vertical Motion

In the vertical direction, the only force acting is gravity:

$$
F_y = -mg
$$

Using Newton's Second Law:

$$
ma_y = -mg \Rightarrow a_y = -g
$$

Which gives a second-order differential equation:

$$
\frac{d^2 y}{dt^2} = -g
$$

Integrating:

$$
\frac{dy}{dt} = v_y(t) = v_0 \sin \theta - g t
$$

$$
y(t) = v_0 \sin \theta \cdot t - \frac{1}{2} g t^2
$$

### 2. Horizontal Motion

There is no horizontal force (neglecting air resistance), so:

$$
F_x = 0 \Rightarrow a_x = 0
$$

So horizontal velocity remains constant:

$$
\frac{dx}{dt} = v_0 \cos \theta
$$

And the horizontal displacement becomes:

$$
x(t) = v_0 \cos \theta \cdot t
$$

### 3. Time of Flight

At the point where the projectile returns to its original vertical level:

$$
y(t) = 0 = v_0 \sin \theta \cdot t - \frac{1}{2} g t^2
$$

Solving for ($ t $):

$$
t = 0 \quad \text{or} \quad t = \frac{2 v_0 \sin \theta}{g}
$$

We take the non-zero solution as the total time of flight.

### 4. Range Derivation

Substitute the time of flight into the horizontal displacement:

$$
R = v_0 \cos \theta \cdot \frac{2 v_0 \sin \theta}{g}
$$

Using the identity ($ \sin 2\theta = 2 \sin \theta \cos \theta $), we simplify:

$$
R = \frac{v_0^2 \sin 2\theta}{g}
$$

## Analysis of the Range

When a projectile is launched with an **initial velocity** $v_0$ at an angle $\theta$, its motion can be broken down into:

- **Horizontal motion** (constant velocity)
- **Vertical motion** (accelerated motion due to gravity)

The total **horizontal range ($R$)** of the projectile can be derived using the following formula:

$$
R = \frac{v_0^2 \sin 2\theta}{g}
$$

where:

- $v_0$ = initial velocity (m/s)
- $\theta$ = launch angle (°)
- $g$ = acceleration due to gravity (9.81 m/s²)

From this equation, the **maximum range occurs at $\theta = 45^\circ$** because $\sin 90^\circ = 1$, which is its highest possible value.

---

## **Experiment Setup**

To simulate the projectile motion experiment, we assumed:

- **Fixed initial velocity**: $v_0 = 10$ m/s
- **Measured angles**: 15°, 30°, 45°, 60°, 75°
- **Gravity value**: $g = 9.81$ m/s²
- **Air resistance ignored**

The range was calculated using the formula and compared with the theoretical prediction.

---

## **Experimental Data & Results**

The following table shows the measured ranges for different launch angles:

| Launch Angle (°) | Calculated Range (m) |
| ------------------- | ---------------------- |
| 15°              | 5.02                 |
| 30°              | 8.84                 |
| 45°              | 10.19                |
| 60°              | 8.84                 |
| 75°              | 5.02                 |

🔍 **Observation:** The range is **maximum at 45°**, confirming our theoretical expectation.

### **Graph:**

The plot below shows the variation of range with launch angle:

- [Colab Link](https://colab.research.google.com/drive/1CnU8XKAxE1OWb8sAe9p_urOHJ_Qsxtui#scrollTo=WxcdxzlqH388)

![Range vs Angle](range_vs_angle.png)

---

## **Discussion**

1. **Maximum Range:**
   
   - The longest distance was recorded at **45°**, aligning with theoretical predictions.
2. **Symmetry in Data:**
   
   - Angles **30° and 60°** yielded the same range.
   - Similarly, **15° and 75°** had equal ranges.

## **Conclusion**

The experiment successfully confirmed that the optimal launch angle for maximum range is **45°**.
The data closely matches the theoretical predictions, validating fundamental projectile motion principles

