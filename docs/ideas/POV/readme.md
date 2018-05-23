# POV
<!--lint disable list-item-indent-->
<!--lint disable list-item-bullet-indent-->

the idea is that the compass needle can rotate slow in both directions to *set* / *point* a direction of choice.

but also can spin up to about 1800rpm (= 30rps) and have LEDs to create a classic POV display.

on every half of the needle are 12..20 LEDs (APA102-2020 or Nichia NSSM124D with TLC5971 or something similar)
so we have a 12..20-Pixel high circle-screen.

---
# Contents
{:.no_toc}

* Will be replaced with the ToC, excluding the "Contents" header
{:toc}
---

## basic calculations

### 130mm Needle, 3mm Pixel Pitch

| name                                       | value   | formula             |
| :----------------------------------------- | ------: | ------------------: |
| updates_per_second = revolution_per_second | 30      |                     |
| pixel_pitch                                | 3mm     |                     |
| needle_diameter                            | 130mm   |                     |


## infrared data transmission
[look at pov_data.md](pov_data.md)

## motor
[look at pov_motor.md](pov_motor.md)

## 3D
- [more research & brainstorming at POV_3D/](POV_3D/)

---
