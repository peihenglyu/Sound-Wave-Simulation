# Sound-Wave-Simulation

---
jupyter:
  kernelspec:
    display_name: env
    language: python
    name: python3
  language_info:
    codemirror_mode:
      name: ipython
      version: 3
    file_extension: .py
    mimetype: text/x-python
    name: python
    nbconvert_exporter: python
    pygments_lexer: ipython3
    version: 3.8.16
  nbformat: 4
  nbformat_minor: 2
  orig_nbformat: 4
---

::: {.cell .markdown}

------------------------------------------------------------------------
:::

::: {.cell .markdown}
`<font size="5">`{=html}A Low-Resolution Approach to Simulate 3D Space
Sound Wave`</font>`{=html}
:::

::: {.cell .markdown}
`<img src="https://drive.google.com/uc?export=download&id=1CWPl6SvKi1eiyztICENNIO4bYR9Uc9qY" title="Sound Wave" width=500 >`{=html}
:::

::: {.cell .markdown}
Method: Simulating Sound Waves with Mesh Points

The demo for this project can be viewed in the sound.html file included
in the submission. (The animation may not be completely stable, so if it
becomes slow or crashes, please refresh the page.) In the animation, a
3D room is simulated, with sound waves represented by numerous points.
These points mimic the physical behavior of sound waves at a lower
resolution. The main idea behind this method is to capture the
reverberation characteristics of any 3D space, as long as the boundaries
of the space are provided.

    Feature 1: Point Movement
    The positions of the points are updated using the formula x[i] = x[i-1] + v * dt, where x[i] represents the position of a point at frame i, v is the velocity of sound, and dt is the time difference between each frame.

    Feature 2: Tracked Gain
    The gain of each point is also tracked. When a point is detected by the microphone, its delay and gain can be determined. Points with lower gain values will have reduced opacity until they disappear completely.

    Feature 3: Microphone Simulation
    The microphone shares the same position as the sound source, represented by a static red point. When a sound wave point is within a certain distance threshold from the microphone, it will also be displayed in red. This allows for a visual representation of points detected by the microphone.
:::

::: {.cell .markdown}
`<img src="https://drive.google.com/uc?export=download&id=1uOO_KzGXKfDfS-gVgGODF-m4-W_fwAC7" title="Sound Wave" width=1000 >`{=html}
:::

::: {.cell .markdown}
Parameters:

    number of points: The resolution of the sound wave, more points bring fancier simulation of sound wave, but too many points may crash the animation.

    mic x: The position of microphon, lower x will move microphone to the left side of the room

    mic y: The position of microphon, lower y will move microphone to the bottom of the room,

    mic z: The position of microphon, lower z will move microphone farther away from the camera.

    time ratio (s): Scale of time. 0.01 means time will pass 100x slower than real word

    room size (m): Size of the simulated area in meter.

    number of frame: How many frames of data are used to draw the delay and gain plot.

The microphone is initially located at position \[0, 0, 0\]. The domain
of the simulated room\'s axes ranges from \[-1, -1, -1\] to \[1, 1, 1\].

When the total frames counter displayed at the bottom left of the page
reaches the \"number of frames\" parameter, a delay and gain plot will
appear on the right side of the animation. You may need to scroll the
page to the right to view it.
:::

::: {.cell .markdown}

------------------------------------------------------------------------
:::

::: {.cell .markdown}
    Example 1:
    Parameters:
    number of points:2000
    mic x: 0
    mic y: -0.9
    mic z: 0
    time ratio (s): 0.1
    room size (m): 100
    number of total frame used for generating plot: 10000
:::

::: {.cell .markdown}
`<img src="https://drive.google.com/uc?export=download&id=1DUnXLGqaKXXuvraxtuloMyq8D9S69pOX" title="Sound Wave" width=500 >`{=html}
`<img src="https://drive.google.com/uc?export=download&id=1_bS5b5MJN0zSmy9N5j3k_RrxjO2TrbzI" title="Sound Wave" width=1000 >`{=html}
:::

::: {.cell .markdown}
    Example 2:
    Parameters:
    number of points:2000
    mic x: 0
    mic y: 0
    mic z: 0
    time ratio (s): 0.01
    room size (m): 10
    number of total frame used for generating plot: 10000
:::

::: {.cell .markdown}
`<img src="https://drive.google.com/uc?export=download&id=1xSf9T6Agzdx0rYnZpughlkZA9YteYYnG" title="Sound Wave" width=1000 >`{=html}
:::

::: {.cell .markdown}
    Example 3:
    Parameters:
    number of points:2000
    mic x: 0
    mic y: 0
    mic z: 0
    time ratio (s): 0.01
    room size (m): 10
    number of total frame used for generating plot: 25000
:::

::: {.cell .markdown}
`<img src="https://drive.google.com/uc?export=download&id=1dnNrX23h0B_Wm-go6bqZnfrjk7_94H-K" title="Sound Wave" width=1000 >`{=html}
:::

::: {.cell .markdown}
    Example 4:
    Parameters:
    number of points:2000
    mic x: 0
    mic y: 0
    mic z: 0
    time ratio (s): 0.1
    room size (m): 100
    number of total frame used for generating plot: 10000
:::

::: {.cell .markdown}
`<img src="https://drive.google.com/uc?export=download&id=1yido4UxQrEq8LTg_OI1KPYEnVx2IF0uY" title="Sound Wave" width=1000 >`{=html}
:::

::: {.cell .markdown}

------------------------------------------------------------------------
:::

::: {.cell .markdown}
Conslusion:

This method offers a relatively reasonable simulation of sound waves in
a 3D space, with both advantages and disadvantages.

    Pros:
    1. Versatility: This approach can be applied to various spaces, as long as the shape of the space is provided.
    2. Customizable resolution: Users can balance the accuracy of the results and computational cost by adjusting the resolution of the sound wave.

    Cons:
    1. Performance dependency: The animation relies on real-time rather than system time, meaning that the accuracy of the data and the smoothness of the animation can be affected by the performance of the browser and computer. Lower frame rates may lead to unexpected results.
    2. Simplified sound wave capture: The current method of tracking sound waves by monitoring the distance between points and the microphone might not be realistic enough. A more accurate approach would involve connecting points to form a sphere-like object and tracking whether any part of the object's surface has passed through the microphone's position. This could potentially yield better results.
:::

::: {.cell .markdown}

------------------------------------------------------------------------
:::

::: {.cell .markdown}
Future Work:

    1. Separate sound and microphone: Allow the sound source and microphone to be placed at different locations for a more realistic simulation.
    2. Multiple sound sources: Introduce multiple sound sources to explore complex sound wave interactions.
    3. Improved gain loss simulation: Currently, the gain is reduced based on the distance a point has traveled. A system should be implemented to simulate gain loss when sound waves bounce back from walls. This would provide a more accurate representation of how sound waves lose energy as they propagate through the environment and reflect off surfaces.
:::
