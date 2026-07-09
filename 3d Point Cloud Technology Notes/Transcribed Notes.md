***These Notes have been transcribed from image to text using Gemini

**3d Point Cloud Tech**

**1. I Phone**

* Uses (near-infrared) illumination & dot projector
* Basically, the dot projector maps 30k points onto the user's face (matrix of points is predetermined). When this grid hits the 3d face, the grid warps based on depth, kind of forming a sheet shaped exactly like the front of face. This is captured using an infrared camera, and is then put through many triangulation algorithms
* this is why showing a picture of yourself won't unlock the phone, since the 3d shape is not formed.

| Pros | Cons |
| --- | --- |
| • Precise | • short distance |
| • Works in dark (infrared rays) | • less accurate outdoors (infrared interference) |
| • Instant |  |

---

**2. Medical Ultrasound**

* uses crystals, which expand and contract rapidly with electricity. converts electric $\rightarrow$ high frequency mechanical sound waves.
* device pressed against medium, emits acoustic pulses. as pulse travels through layers, it encounters acoustic disturbance. Only a portion of wave returns using many signals, depth is calculated

| Pros | Cons |
| --- | --- |
| • Can penetrate solids, opaque, and murky mediums. | • Point clouds are not "sharp" |
| • Radiation free | • Not effective in open air, sound propagates worse. |
| • Cheap |  |

**3. LiDAR**

* Fires millions of lasers per second in all directions coordinates calculated based on time taken.
* Very similar to video 1 & 2

| Pros | Cons |
| --- | --- |
| - large range & speed | - costly |
| - real 3d geometry | - not effective in bad weather (lasers are interfered with) |
| - day & night |  |
