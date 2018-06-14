# Test Table Calc
<!--lint disable list-item-indent-->
<!--lint disable list-item-bullet-indent-->
<!--lint disable code-block-style-->


| name                                       | value     | formula                                              | value |
| :----------------------------------------- | --------: | ---------------------------------------------------: | ----: |
| updates_per_second = revolution_per_second | 30        |                                                      | <label class="unit rpm"><input type="number" value="30" step="1" min="0" max="120"/></label> |
| pixel_pitch                                | 3mm       |                                                      | <label class="unit millimeter"><input type="number" value="3" step="0.1" min="0" max="20" /></label> |
| needle_diameter                            | 130mm     |                                                      | <label class="unit millimeter"><input type="number" value="130" step="1" min="0" max="500" /></label> |
| pixel_count_one_side                       | 20        | toFixed(needle_diameter / pixel_pitch; 0)            | <span class=""></span> |
| pixel_count_total                          | 40        | pixel_count_one_side * 2                             | <label class=""><input type="number"   value="40" step="1" min="0" max="1000" /></label> |
| pixel_circumference                        | 408mm     | toFixed(π * needle_diameter; 1)                      | <span class="unit millimeter"></span> |
| pixel_circ_vcount                          | 136       | toFixed(pixel_circumference / pixel_pitch)           | <label class=""><input type="number"   value="136" step="1" min="0" max="1440" /></label> |
| pixel_updates_per_revolution               | 136       | pixel_circ_vcount                                    | <span class=""></span> |
| duration_per_revolution                    | 33ms      | toFixed(1000 / updates_per_second; 1)                | <span class="unit milliseconds"></span> |
| duration_per_pixel                         | 242us     | toFixed((duration_per_revolution / pixel_circ_vcount) * 1000; 0) | <span class="unit microseconds"></span> |
| pixel_pwm_duration_for_8bit                | 945ns     | toFixed((duration_per_pixel * 1000) /   256; 0)      | <span class="unit nanoseconds"></span> |
| pixel_pwm_rate_for_8bit                    | 1,06MHz   | toFixed(1000 / pixel_pwm_duration_for_8bit ; 2)      | <span class="unit megahertz"></span> |

<button type="button" name="bt_update" id="bt_update">update</button>

<script src="{{ '/assets/js/table_calc_example.js?v=' | append: site.github.build_revision | relative_url }}" charset="utf-8"></script>
<script type="text/javascript">


</script>



```
reminder / helper

1 s                  = 1Hz
1 000 ms             = 1Hz
1 000 000 us         = 1Hz
1 000 000 000 ns     = 1Hz
1 000 000 000 000 ps = 1Hz

1s  = 1Hz
1ms = 1kHz
1us = 1MHz
1ns = 1GHz
1ps = 1THz
```
