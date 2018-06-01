# legacySrepTransformer
# author: Zhiyuan Liu
# date: 2018.6.1 Happy Children's Day

The purpose of this project is to transform legacy srep to new srep in two ways:
a. The format of files: from m3d file to header.xml plus 3 vtp files
b. Divide fold points on skeleton from their partners

Usage:
python legacyTransformer.py xxx.m3d outputPrefix [optional:epsilon]

Example:
python legacyTransformer test_data/hippo.m3d test_data/hippo 0.02

Features:
a. Fix the bug caused by precision error. Need to set medial_points data type to double, it is found when try to apply TPS 
b. Move fold points away from their partners along crest spoke direction. The distance is defined by epsilon.
c. Save new srep to one header.xml along with 3 vtp file: up.vtp, down.vtp and crest.vtp

Test:
The test_data contains 3 legacy srep. For hippo.m3d, it is fine to use default epsilon: 0.02. Yet 
for another 2 sreps, setting epsilon to 0.5 will have better effect.

Visualization:
Try to checkout extension of 3DSlicer at: https://github.com/ZhiyLiu/newSrepVisualizer.git
The effect of test_data could be found in test_data/screenshots
