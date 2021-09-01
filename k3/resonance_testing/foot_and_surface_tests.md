# How is printer resonance affected by different foot materials, equal/unequal pressure on the feet, and the stability of the surface the printer rests on?

The following battery of resonance tests were conducted in the space of a few hours. There were no changes to any moving mass or belt tension between tests. In fact, there were no mechanical changes at all between tests. However, the printer was powered off between some tests.

Prior to conducting these tests, every screw in the gantry and tool head was tightened, with the exception of the screws holding the spacers to the Y rails. The tests were conducted with all panels installed, but without the top hat.

The acelerometer was mounted on the side of the hotend heatsink (facing the front of the printer). It was secured with 3M VHB tape and a zip tie around the heatsink. The axes were mapped in the klipper configuration to match the installed orientation.

Three "table" surfaces were tested:

1. The most stable is on top of a heavy table saw, with additional mass added. The saw is extremely stable and with the added mass on the top, weighs approximately 200kg.
2. A sturdy workbench, which although heavy, is a bit wobbly in the Y-axis of the printer.
3. The same workbench, but shimmed against the wall to add stability.
4. A large foam box, previously a dubious printer enclosure. The box is flexible in all axes and flexed significantly under the weight of the printer.

Three types of feet were tested with the printer on the table saw:

1. Bare screws
2. Soft feet. These are the standard K3 foot body, but printed in TPU, and without the cushioned inserts.
3. Hard feet. Standard K3 foot body printed in ASA, with TPU inserts

For each foot type and on the table saw, resonance tests were done with the feet shimmed such that each foot had even pressure and also with the feet shimmed such that the feet had uneven pressure. Gauging of pressure was done "by feel". With the screw and hard feet, uneven pressure meant that one foot was slightly off the table surface. With soft feet, there was enough flex in the feet that even with significantly uneven loading, every foot was still in contact with the table surface.

Finally, repeated tests were performed without re-homing and issuing `set_kinematic_position` between each test to offset one axis by a few microsteps to see if extremely precise positioning was required between tests to get consistent results.

Graphs were produced with a modified version of the `calibrate_shaper.py` script included with klipper. The script was modified to remove the shaper reduction plot and recommendations, and also to manually specify the scale of the plots' Y axes. This was done to simplify comparison. **All of the graphs here have fixed scales, though the scale for the X and Y graphs are different.**



## Setup
Table saw with added mass|Workbench|Foam Box
-|-|-
![](https://github.com/StrikeEagleCC/3D_Printing/blob/main/k3/images/resonance_tests/printer_on_saw_with_added_mass.jpg)|![](https://github.com/StrikeEagleCC/3D_Printing/blob/main/k3/images/resonance_tests/printer_on_braced_bench.jpg)|![](https://github.com/StrikeEagleCC/3D_Printing/blob/main/k3/images/resonance_tests/printer_on_foam_box.jpg)

Screw Feet|Soft Feet|Hard Feet
-|-|-
![](https://github.com/StrikeEagleCC/3D_Printing/blob/main/k3/images/resonance_tests/screw_feet.jpg)|![](https://github.com/StrikeEagleCC/3D_Printing/blob/main/k3/images/resonance_tests/soft_feet.jpg)|![](https://github.com/StrikeEagleCC/3D_Printing/blob/main/k3/images/resonance_tests/hard_feet.jpg)


### Test 1:
Setup: table saw, screw feet, even pressure

<img src="https://github.com/StrikeEagleCC/3D_Printing/blob/main/k3/images/resonance_tests/01_x_saw_screws_shimmed.png" width="400" /><img src="https://github.com/StrikeEagleCC/3D_Printing/blob/main/k3/images/resonance_tests/01_y_saw_screws_shimmed.png" width="400" />

Notes: These results are highly unusual, and were not repeatable. Why this test is such a dramatic outlier is unclear.


### Test 2:
Setup: table saw, soft feet, even pressure

<img src="https://github.com/StrikeEagleCC/3D_Printing/blob/main/k3/images/resonance_tests/02_x_saw_soft_feet_shimmed.png" width="400" /><img src="https://github.com/StrikeEagleCC/3D_Printing/blob/main/k3/images/resonance_tests/02_y_saw_soft_feet_shimmed.png" width="400" />


### Test 3:
Setup: table saw, soft feet, uneven pressure

<img src="https://github.com/StrikeEagleCC/3D_Printing/blob/main/k3/images/resonance_tests/03_x_saw_soft_feet_unshimmed.png" width="400" /><img src="https://github.com/StrikeEagleCC/3D_Printing/blob/main/k3/images/resonance_tests/03_y_saw_soft_feet_unshimmed.png" width="400" />


### Test 4:
Setup: table saw, hard feet, even pressure

<img src="https://github.com/StrikeEagleCC/3D_Printing/blob/main/k3/images/resonance_tests/04_x_saw_hard_feet_shimmed.png" width="400" /><img src="https://github.com/StrikeEagleCC/3D_Printing/blob/main/k3/images/resonance_tests/04_y_saw_hard_feet_shimmed.png" width="400" />


### Test 5:
Setup: table saw, hard feet, uneven pressure

<img src="https://github.com/StrikeEagleCC/3D_Printing/blob/main/k3/images/resonance_tests/05_x_saw_hard_feet_unshimmed.png" width="400" /><img src="https://github.com/StrikeEagleCC/3D_Printing/blob/main/k3/images/resonance_tests/05_y_saw_hard_feet_unshimmed.png" width="400" />


### Test 6:
Setup: table saw, screw feet, even pressure

<img src="https://github.com/StrikeEagleCC/3D_Printing/blob/main/k3/images/resonance_tests/06_x_saw_screws_shimmed.png" width="400" /><img src="https://github.com/StrikeEagleCC/3D_Printing/blob/main/k3/images/resonance_tests/06_y_saw_screws_shimmed.png" width="400" />

Notes: This test was an attempt to replicate the first test.


### Test 7:
Setup: table saw, screw feet, uneven pressure

<img src="https://github.com/StrikeEagleCC/3D_Printing/blob/main/k3/images/resonance_tests/07_x_saw_screws_unshimmed.png" width="400" /><img src="https://github.com/StrikeEagleCC/3D_Printing/blob/main/k3/images/resonance_tests/07_y_saw_screws_unshimmed.png" width="400" />


### Test 8:
Setup: un-braced bench, hard feet, even pressure

<img src="https://github.com/StrikeEagleCC/3D_Printing/blob/main/k3/images/resonance_tests/08_x_bench_hard_feet_shimmed.png" width="400" /><img src="https://github.com/StrikeEagleCC/3D_Printing/blob/main/k3/images/resonance_tests/08_y_bench_hard_feet_shimmed.png" width="400" />


### Test 9:
Setup: braced bench, hard feet, even pressure

<img src="https://github.com/StrikeEagleCC/3D_Printing/blob/main/k3/images/resonance_tests/09_x_bench_braced_hard_feet_shimmed.png" width="400" /><img src="https://github.com/StrikeEagleCC/3D_Printing/blob/main/k3/images/resonance_tests/09_y_bench_braced_hard_feet_shimmed.png" width="400" />


### Test 10:
Setup: foam box, hard feet, even pressure

<img src="https://github.com/StrikeEagleCC/3D_Printing/blob/main/k3/images/resonance_tests/10_x_foam_box_hard_feet_unshimmed.png" width="400" /><img src="https://github.com/StrikeEagleCC/3D_Printing/blob/main/k3/images/resonance_tests/10_y_foam_box_hard_feet_unshimmed.png" width="400" />
