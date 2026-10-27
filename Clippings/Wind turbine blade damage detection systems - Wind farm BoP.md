---
title: "Wind turbine blade damage detection systems - Wind farm BoP"
source: "https://www.windfarmbop.com/wind-turbine-blade-damage-detection-systems/"
author:
  - "[[Francesco Miceli]]"
published: 2020-03-28
created: 2026-10-25
description: "Wind turbine blades are rarely subject to catastrophic failures, although you can find a bunch of videos on YouTube with blades flying away or falling into pieces. They are however subject to several problems, such as cracks, debonding of the various layers, internal delamination, etc. As an order of magnitude blade failures are accountable for"
tags:
  - "clippings"
---
![](https://www.windfarmbop.com/wp-content/uploads/2020/03/Typical-damages-to-WTGs-blades.jpg)

Wind turbine blades damages. B.F. Sørensen, E. Jørgensen, C.P. Debel, H.M. Jensen, T.K. Jacobsen, K. Halling, et al., Improved design of large wind turbine blade of fibre composites based on studies of scale effects (phase 1). summary report.

Wind turbine blades are rarely subject to catastrophic failures, although you can find a bunch of videos on YouTube with blades flying away or falling into pieces.

They are however subject to several problems, such as cracks, debonding of the various layers, internal delamination, etc.

As an order of magnitude blade failures are accountable for approximately one fifth of the problems usually seen during the operational life of the wind farm.

Such problems have a direct impact on the profitability of the plant and can be extremely expensive to fix.

Some issues can be fixed leaving the blade attached to the rotor. However not all problems can be solved without dismantling the blade, and the fee associated with the cranes needed for the dismantling can be very high.

In the worst case scenario a blade substitution will be needed, and the transportation cost will add up.

A certain number of failure is attributable to design error (insufficient material strength under fatigue or extreme loads) or manufacturing problems.

However the overwhelming majority of issues seem to be attributable to extreme weather – basically strong winds, thunderstorm (including lightning strikes), ice, pollutants, etc.

The effect of ice accumulation is especially dangerous in case of asymmetrical accumulation, because it can create unbalanced loads in the rotor.

Pollutants, usually in the form of airborne particles (e.g. sand) can shorten the life of the blades accelerating the erosion of the superficial layer. A gel coat usually cover the outside of the blade to protect it from ultraviolet degradation, water, etc.

Therefore the erosion of the external layer may have two impacts: lower the efficiency of the blade (this will have a direct impact on energy production, and ultimately on money) and accelerating the degradation of the blade.

Some areas of the blades are more prone to damage: tip, root and joints accumulate the majority of reported damages. The distribution of failures has however a typical pattern: erosion is more frequent in the tip side (due to the higher local speed) while cracks are more frequent toward the root.

![](https://www.windfarmbop.com/wp-content/uploads/2020/03/Blades-crack-and-erosion-regions.jpg)

Blades crack and erosion regions. Zhang, H., 2016. Reducing Uncertainty in Wind Turbine Blade Health Inspection with Image Processing Techniques. Iowa State University, Ames, Iowa

A variety of methods has been developed to detect and monitor damage. There is a consensus on the fact that early detection of a problem mean usually lower maintenance costs.

The “perfect”, ideal method should be able to assess the full scale of the blade without contact, allowing for continuous remote monitoring.

Unfortunately such methods does not exist yet. Among the most promising techniques it is worth mentioning:

The use of **strain sensors**, either embedded in the blade or on the surface. It is the same type of fibre-optic called “fibre Bragg gratings” (FBGs) that I have described in [another post.](http://www.windfarmbop.com/long-term-instrumented-monitoring-of-wind-turbine-foundations-cracks-evolution/) As each sensor measure only direct strain and shear strain only in one point of the blades many sensors will be needed to have the full picture. Another problem is that the sensor can give a “false positive” result if it fails due to creep, fatigue, etc.

Measuring the **acoustic emissions** of the blade is another extremely interesting method to find damages. Unfortunately it is a complex system that need many sensors and physical contact with the blade of many sensors – something that could be difficult to achieve in operational wind farms. Sensors operate on an extended frequency range (50 kHz to 1 MHz) and as in the case of the strain sensor are used not only for the blades but also for the other components (gearbox, bearings, etc.)

**Ultrasound** is an extremely common non-destructive technique, that basically analyse the ultrasound waves reflected by the different layers of materials and by discontinuities in the materials. The main problem of ultrasound detection is that usually physical surface contact is needed. On top of that, there is also usually time consuming (and it can be hard to process the signal). It can however be extremely useful for an in depth analysis of the situation of the blade.

**Thermography** is a technique that use infrared cameras to assess the temperature distribution. If there is a defect in the structure the flow of the heat will be disrupted, causing temperature gradients. Thermography comes in two types, passive (made from the ground using the “natural” temperature) and active (heating the surface).

The last method, and possibly one of the most promising giving the quick evolution of computer computational power, is **Machine Vision**. One or more cameras are used to capture images of the blades subsequently analysed with image processing algorithms.

There are several interesting studies on machine learning – basically using two set of image, one of blades with known failures and the other of blades without problems, to “train” the algorithm to detect issues.