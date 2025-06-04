# Measuring Earth's Gravitational Acceleration with a Pendulum

## Motivation

The acceleration 
 due to gravity is a fundamental constant that influences a wide range of physical phenomena. Measuring $g$ accurately is crucial for understanding gravitational interactions, designing structures, and conducting experiments in various fields. One classic method for determining $g$ is through the oscillations of a simple pendulum, where the period of oscillation depends on the local gravitational field.

### Materials

- String ( ~1 meter)
- Key chain
- Measure(precision ±0.001 m)
- Stopwatch (Smartphone) (precision ±0.01 s)

### 📊 Data

| Measurement  | $T_{10}$ (s) |
|---------------|--------------|
| 1             | 17.55        |
| 2             | 18.97        |
| 3             | 19.15        |
| 4             | 19.38        |
| 5             | 18.97        |
| 6             | 18.98        |
| 7             | 19.08        |
| 8             | 18.85        |
| 9             | 19.17        |
| 10            | 19.13        |

 ### 🧮 Calculations

#### 1. Mean Time:

$$
\bar{T}_{10} = \frac{1}{10} \sum t_i = \frac{189.23}{10} = 18.923\ \text{s}
$$

---

#### 2. Standard Deviation:

$$
\sigma_T = \sqrt{\frac{1}{n - 1} \sum (t_i - \bar{T}_{10})^2} \approx 0.504\ \text{s}
$$

---

#### 3. Uncertainty in the Mean:

$$
\Delta T_{10} = \frac{\sigma_T}{\sqrt{n}} = \frac{0.504}{\sqrt{10}} \approx 0.159\ \text{s}
$$

---

#### 4. Period of the Pendulum:

$$
T = \frac{\bar{T}_{10}}{10} = \frac{18.923}{10} = 1.892\ \text{s}
$$

$$
\Delta T = \frac{\Delta T_{10}}{10} = \frac{0.159}{10} = 0.016\ \text{s}
$$

---

#### 5. Gravitational Acceleration:

$$
g = \frac{4 \pi^2 L}{T^2} = \frac{4 \pi^2 \cdot 1.00}{(1.892)^2} \approx 11.03\ \text{m/s}^2
$$

---

#### 6. Uncertainty in $g$:

$$
\frac{\Delta g}{g} = \sqrt{\left(\frac{\Delta L}{L}\right)^2 + \left(2 \cdot \frac{\Delta T}{T}\right)^2}
= \sqrt{\left(\frac{0.0005}{1.00}\right)^2 + \left(2 \cdot \frac{0.016}{1.892}\right)^2}
\approx 0.0176
$$

$$
\Delta g = 0.0176 \cdot 11.03 \approx 0.19\ \text{m/s}^2
$$

---

### ✅ Final Result:

$$
g = 11.03 \pm 0.19\ \text{m/s}^2
$$




### 🔍 Analysis and Discussion

#### 1. Comparison with Standard Value:

The experimentally measured value of gravitational acceleration is:

$$
g = 11.03 \pm 0.19\ \text{m/s}^2
$$

The accepted standard value is:

$$
g_{\text{standard}} = 9.81\ \text{m/s}^2
$$

The measured value is higher than the standard, and the discrepancy exceeds the calculated uncertainty. This suggests the presence of systematic errors or assumptions that may not hold.

---

#### 2. Discussion of Uncertainty Sources:

- **Length Measurement ($\Delta L$):**  
  The uncertainty in length was small due to the use of a tape measure with 1 mm resolution. However, measuring from the suspension point to the center of mass may introduce a slight error if not done precisely.

- **Timing Uncertainty ($\Delta T$):**  
  Human reaction time is a major source of uncertainty in using a stopwatch. This can cause random errors and affects the repeatability of the measurement. Using longer timing intervals (e.g., 10 oscillations) helps reduce this impact.

- **Air Resistance and Amplitude:**  
  Although the initial angle was kept below $15^\circ$, damping and small deviations from ideal behavior can influence the period. Air resistance slightly lengthens the period and leads to underestimation of $g$.

---

#### 3. Experimental Limitations:

- Manual timing introduces significant human error.
- Assumption of no damping and ideal pendulum behavior may not hold.
- Slight misalignment or variation in amplitude could affect consistency.

> Overall, the experiment provides a reasonable estimate for $g$, but improvements in timing accuracy and minimizing systematic errors would enhance reliability.
