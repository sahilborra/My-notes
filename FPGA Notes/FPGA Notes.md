Transcribed Using Gemini

### **[Field Programmable Gate Array Data Pipeline & Visualization]**

#### **Why Field Programmable Gate Array (FPGA)?**

* **Central Processing Unit (CPU) (sequential)** $\mathbf{\times}$
* $\rightarrow$ reads each microphone one-by-one
* $\rightarrow$ very slow


* **Field Programmable Gate Array (FPGA) (parallel)** $\mathbf{\checkmark}$
* $\rightarrow$ processes 100+ audio streams simultaneously



---

#### **How it works**

##### **Step 1: Parallel Ingestion**

* Microphone 1 Data $\rightarrow$ Input pin 1 $\mathbf{\backslash}$
* Microphone 2 Data $\rightarrow$ Input pin 2 $\rightarrow$ All enter FPGA @ same millisecond
* Microphone "N" Data $\rightarrow$ Input pin N $\mathbf{/}$

##### **Step 2: Time Shift (First In, First Out (FIFO) Alignment)**

* $\rightarrow$ The FPGA uses FIFO buffers to delay fast streams until slower ones catch up

| Raw waves (unaligned) | Delay | Aligned Waves |
| --- | --- | --- |
| Microphone 1: $\ \ 1 \ \ 0 \ \ 1 \ \ - \ \ - \ \  | no delay | $1 \ \ 0 \ \ 1$ |
| Microphone 2: $\ \ - \ \ 1 \ \ 0 \ \ 1 \ \ - \ \ -$ | shift left 1 | $1 \ \ 0 \ \ 1$ |
| Microphone 3: $\ \ - \ \ - \ \ 1 \ \ 0 \ \ 1 \ \ -$ | shift left 2 | $1 \ \ 0 \ \ 1$ |

Shift amount is decided by time delay:


$$\Delta t = \frac{\Delta d}{c}$$

---

##### **Step 3 - Testing the Pixels**

* The FPGA adds all aligned microphone numbers to test a specific coordinate
* $\rightarrow$ **constructive interference:** waves line up. Numbers pile up into large numerical spike ($1 + 1 + 1 = 3$)
* $\rightarrow$ **destructive interference (background noise):** waves are mismatched, they cancel each other out ($1 + (-1) + 0 = 0$)


* **Constructive**
* Wave 1 $\land$ + Wave 2 $\land$ + Wave 3 $\land$ = **(huge spike)** *(Visualized as a large triangular peak)*


* **Destructive**
* Wave 1 $\land$ + Wave 2 $\lor$ = **(flat / silence)**



---

##### **Step 4 - Visual Overlay Mixing**

* **Low-Resolution Acoustic Grid** $\rightarrow$ *(Stretch sound grid to match video size)* $\mathbf{\backslash}$
* **High-Resolution Camera Grid** $\rightarrow \mathbf{/}$

$$\rightarrow \text{Upscaling} \rightarrow \text{Color Mapping} \rightarrow \text{Blending} \rightarrow \text{Final Image}$$

* **Color Mapping details:**
* Huge Spike = Red
* Zero noise = Transparent


* **Blending details:**
* Blends color map at 50% over the video
