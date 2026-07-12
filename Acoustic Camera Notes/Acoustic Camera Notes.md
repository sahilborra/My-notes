Transcribed Using Gemini

---

### **[Ultrasound Acoustic Sensors]**

#### **Concept**

* **Acoustic Camera** = Normal camera + Array of microphones.
* **Output** = Live video with heat map overlay (inaudible)
* **Target** = Ultrasound signals $> 20\text{kHz}$

Invisible Sound Source $\rightarrow$ Camera Array $\rightarrow$ Screen Display

*(Diagram: Displays a "Source" connected by dashed lines $d_1$ and $d_2$ to a horizontal baseline consisting of a left `microphone`, a central `camera`, and a right `microphone`.)*

#### **How it works**

* 100+ microphones
* Sound hits each microphone @ different time
* **"Acoustic Beamforming"**
* $\rightarrow$ computer calculates delays
* $\rightarrow$ triangulate X, Y coordinate of source
* $\rightarrow$ filter out low frequency background noise



---

#### **Applications**

1. **Electronic Faults**
* partial discharge (small sparks)
* corona (ionization of air around voltage lines)
* Insulation break down (failure of insulators)


2. **Gas Leaks**
* compressed air (pressurized air)
* specialty gases (leak of expensive gases)
* can quantify loss (need advanced camera)


3. **Mechanical Failure**
* bearing wear (bearings deforming / losing lubricant)
* misalignment
* friction



---

#### **Math**

*(Diagram: A triangle with a top vertex labeled **Sound Source $(x, y)$**. The bottom-left vertex is **Microphone 1 $(0,0)$** which "Receives at $t_1$". The bottom-right vertex is **Microphone 2 $(L,0)$** which "Receives at $t_2$". The left leg is labeled $d_1$, the right leg is $d_2$, and the base length is $L$.)*

1. **Time delay**

$$\Delta t = t_2 - t_1$$


2. **Distance Difference**

$$\Delta d = d_2 - d_1$$


$$\rightarrow \Delta d = c \cdot \Delta t$$


$$c = \text{speed of sound} = 343\text{ms}^{-1}$$


3. **Intersection (Finding $x$ & $y$)**

$$d_1 = \sqrt{x^2 + y^2}$$


$$d_2 = \sqrt{(x-L)^2 + y^2}$$


*Substitute:*

$$\sqrt{(x-L)^2 + y^2} - \sqrt{x^2 + y^2} = c \cdot \Delta t$$


Since we only use two microphones, we get a single hyperbola (no real answer)
the more microphones we add, the more accurate the reading is.
