# How do different umbilical materials affect toolhead deflection?

The purpose of these tests was to compare how much deflection of the toolhead was attributable to forces imparted by the umbilical cable with different cable construction. The test platform was an Annex-Engineering K3.

4 types of umbilical construction were tested:

1. 16 20awg conductors stripped from a found cable: SMC IZS41-CPZ
    1. each conductor is very high strand count and has fairly thin but rigid insulation, presumably PVC.
    1. the conductors are bundled loosely in 15mm id braided sleeving
1. igus chainflex CF130-05-18-UL ([McMaster](https://www.mcmaster.com/8082K15/),[igus](https://www.igus.com/product?artNr=CF130-05-18-UL))
    1. 18 conductors, 20awg
1. Hua Xun Tong TRVV 300/300V 16x0.5mm^2 ([AliExpress](https://www.aliexpress.com/item/4000785485299.html?spm=a2g0o.productlist.0.0.1e465046fgzUNI&algo_pvid=666d82f1-6bb2-4d2b-871c-c2151e893432&algo_exp_id=666d82f1-6bb2-4d2b-871c-c2151e893432-2&pdp_ext_f=%7B%22sku_id%22%3A%2210000007818111643%22%7D))
1. 3 cable bundle from automation direct
    1. 2 runs Quabbin continuous flexing Cat5e industrial Ethernet ([automation direct](https://www.automationdirect.com/adc/shopping/catalog/cables/bulk_multi-conductor_cable/continuous_flexing_industrial_ethernet_cable/unshielded/q5752-1))
    1. 1 run igus chainflex CF9-03-03 ([automation direct](https://www.automationdirect.com/adc/shopping/catalog/cables/bulk_multi-conductor_cable/continuous_flexing_control_cable/20_awg_unshielded/cf5-05-03-1))
    1. jackets not removed, bundle loosely within 15mm id braided sleeve


Ranked by increasing flexibility: #2, #3, #4, #1


The length of the umbilical was determined more or less by feel for each. Cables #2 and #3 ended up at 300mm, measured from the cable gland to the bottom of the umbilical mount. Cables #1 and #4 were about 290mm.

When choosing the best umbilical length for use in the K3, an important consideration is whether a top hat will be used. If the top hat is used, care must be taken to ensure the umbilical is not so long that it presses against the inside of the top hat. However, at lengths short enough to avoid, this, the umbilical can get pulled fairly taught at some toolhead positions. For this test, I sized the cables such that they contacted the top hat, but did not press hard enough to dislodge it from the magnetic mounts. Tests were conducted with and without the top hat installed. If the top hat will not be used, longer umbilicals can be used that will not put as much pressure on the toolhead.


### Measurement method for Z deflection:

1. Install umbilical
2. home, z_tilt_adjust, bed_mesh_calibrate (no tophatmesh)
3. install tophat 
4. repeat step 2 (tophat mesh)
5. remove tophat and umbilical
6. repeat step 2 (baseline mesh)

The method used for measuring deflection in the X and Y axis was poorly controlled, and the data gathered was imprecise and not very repeatable. Therefore, that data will not be included here. I currently have no plans to improve or repeat those tests.

Analysis method:

For each umbilical type, the following comparisons were made:

* no tophat mesh vs baseline mesh
* tophat mesh vs baseline mesh
* no tophat mesh vs tophat mesh

For easy viewing, comparisons were made by calculating the difference for each mesh point and building a new mesh with the results, and adding the resulting mesh to my printer.conf to be viewed in fluidd. 

**IMPORTANT:** the meshes shown here are the calculated comparisons, not the actual meshes measured.



### Mesh variance summary (as displayed in fluidd)

Umbilical|No tophat vs baseline|With tophat vs baseline|No tophat vs with tophat
-|-|-|-
1|0.0092|no data|no data
2|0.0508|0.0703|0.0296
3|0.0239|0.0369|0.0191
4|0.0242|0.0341|0.0177


## Mesh Comparisons


### Cable #1 (16 individual 20awg conductors )

No tophat vs baseline: variance=0.0092mm

<img src="https://github.com/StrikeEagleCC/3D_Printing/blob/main/k3/images/umbilical_meshes/cable1_no_tophatvs_baseline_0092.png" width="400" />

Note: I forgot to test with the tophat installed.



### Cable #2 (igus chainflex CF130-05-18-UL)

No tophat vs baseline: variance=0.0508mm

<img src="https://github.com/StrikeEagleCC/3D_Printing/blob/main/k3/images/umbilical_meshes/cable2_no_tophat_vs_baseline_0508.png" width="400" />

Tohpat vs baseline: variance=0.0703mm

<img src="https://github.com/StrikeEagleCC/3D_Printing/blob/main/k3/images/umbilical_meshes/cable2_tophat_vs_baseline_0703.png" width="400" />

Tophat vs no tophat: variance=0.0296mm

<img src="https://github.com/StrikeEagleCC/3D_Printing/blob/main/k3/images/umbilical_meshes/cable2_tophat_vs_no_tophat_0296.png" width="400" />



### Cable #3 (Hua Xun Tong)

No tophat vs baseline: variance=0.0239mm

<img src="https://github.com/StrikeEagleCC/3D_Printing/blob/main/k3/images/umbilical_meshes/cable3_no_tophat_vs_baseline_0239.png" width="400" />

Tohpat vs baseline: variance=0.0369mm

<img src="https://github.com/StrikeEagleCC/3D_Printing/blob/main/k3/images/umbilical_meshes/cable3_tophat_vs_baseline_0369.png" width="400" />

Tophat vs no tophat: variance=0.0191mm

<img src="https://github.com/StrikeEagleCC/3D_Printing/blob/main/k3/images/umbilical_meshes/cable3_tophat_vs_no_tophat_0191.png" width="400" />



### Cable #4 (3 cable bundle)

No tophat vs baseline: variance=0.0242mm

<img src="https://github.com/StrikeEagleCC/3D_Printing/blob/main/k3/images/umbilical_meshes/cable4_no_tophat_vs_baseline_0242.png" width="400" />

Tohpat vs baseline: variance=0.0341mm

<img src="https://github.com/StrikeEagleCC/3D_Printing/blob/main/k3/images/umbilical_meshes/cable4_tophat_vs_baseline_0341.png" width="400" />

Tophat vs no tophat: variance=0.0177mm

<img src="https://github.com/StrikeEagleCC/3D_Printing/blob/main/k3/images/umbilical_meshes/cable4_tophat_vs_no_tophat_0177.png" width="400" />



### Other notes:

Increased flexibility leads to reduced toolhead deflection, but the need for flexibility must be balanced with cable longevity and safety. Additional vertical space for the umbilical in the K3 might be useful to reduce the impact of umbilical induced toolhead deflection by allowing longer umbilicals to be used.
