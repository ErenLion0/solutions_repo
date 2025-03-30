<script type="text/javascript" async
  src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-mml-chtml.js">
</script>

# 📌 **Investigating the Range as a Function of the Angle of Projection**

## **Problem Statement**

The goal of this experiment is to analyze the relationship between the **launch angle (\\( \\theta \\))** and the **horizontal range (\\( R \\))** of a projectile.

---

## **Theoretical Background**

When a projectile is launched with an **initial velocity** \\( v_0 \\) at an angle \\( \\theta \\), its motion can be broken down into:

- **Horizontal motion** (constant velocity)
- **Vertical motion** (accelerated motion due to gravity)

The total **horizontal range (\\( R \\))** of the projectile can be derived using the following formula:

$$
R = \frac{v_0^2 \sin 2\theta}{g}
$$

where:

- \\( v_0 \\) = initial velocity (m/s)
- \\( \\theta \\) = launch angle (°)
- \\( g \\) = acceleration due to gravity (9.81 m/s²)

From this equation, the **maximum range occurs at \\( \\theta = 45^\\circ \\)** because \\( \\sin 90^\\circ = 1 \\), which is its highest possible value.

---

## **Experiment Setup**

To simulate the projectile motion experiment, we assumed:

- **Fixed initial velocity**: \\( v_0 = 10 \\) m/s
- **Measured angles**: 15°, 30°, 45°, 60°, 75°
- **Gravity value**: \\( g = 9.81 \\) m/s²
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

[Colab Link](https://colab.research.google.com/drive/1CnU8XKAxE1OWb8sAe9p_urOHJ_Qsxtui#scrollTo=WxcdxzlqH388)

![Range vs Angle](range_vs_angle.png)

---

## **Discussion**

1. **Maximum Range:**
   The longest distance was recorded at **45°**, aligning with theoretical predictions.
2. **Symmetry in Data:**
   Angles **30° and 60°** yielded the same range.
   Similarly, **15° and 75°** had equal ranges.

## **Conclusion**

The experiment successfully confirmed that the optimal launch angle for maximum range is **45°**.
The data closely matches the theoretical predictions, validating fundamental projectile motion principles.


