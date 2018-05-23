# POV data
<!--lint disable list-item-indent-->
<!--lint disable list-item-bullet-indent-->

idea here is to have a IR led directly pulsing the raw data out and an receiver converting it back to signal..
so this could be transmitted over the rotation contact-less.
challenge here is the bit time - we need some very very fast photo detectors...

---
# Contents
{:.no_toc}

* Will be replaced with the ToC, excluding the "Contents" header
{:toc}
---

## ToDo:
- find / decide which parts to test
- add schematics for
  - led control
  - photodiode / phototransistor handling


## bitrate / update-rate calculations

### 130mm Needle, 3mm Pixel Pitch

| calculation step   | APA102                | TLC5971             | formula               |
| :----------------- | :-------------------- | :------------------ | --------------------: |
| bytes_per_update   | 166 (4 + 40*4 + 2)    | 280 (28 * (40 / 4)) |                       |
| bits_per_update    | 1328                  | 2240                | bytes_per_update * 8  |
| bits_per_second    | 5418240               | 9139200             | bits_per_update * pixel_updates_per_second |
| kbit_per_second    | 5418                  | 9139                |                       |
| Mbit_per_second    | 5,41                  | 9,14                |                       |
| bit_time_max       | 184ns (= 0,184us)     | 109 ns (= 0,109us)  | `1s / (5,41*10^6) ==` |

```
1 second == 1.000 ms == 1.000.000 us == 1.000.000.000 ns

10 bit pro second == 1s/10         per bit == 100ms per bit
10kbit pro second == 1s/10k        per bit == 100us per bit
10Mbit pro second == 1s/10M        per bit == 0,0000001s == 100 ns  
10Mbit pro second == 1s/10.000.000 per bit == 0,0000001s == 100 ns  
```

## schematics

### High-Speed LED driver


### High-Speed Receiver

#### simple Phototransistor

#### Transimpedance Amplifier (TIA)



---
