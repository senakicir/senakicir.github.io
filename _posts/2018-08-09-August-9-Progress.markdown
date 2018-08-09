---
layout: post
title:  "August 9 Progress"
date:   2018-09-08 14:24:58 +0200
categories: progress
---

Following Helge's suggestion, I added a small number to the denominator of a division operation to avoid dividing by 0 (or a very small number). This solved my NaN problem from yesterday!

Here is another experiment with weights: {'proj': 0.0066, 'smooth': 0.53, 'bone': 0.199, 'lift': 0.265} and 4000 iterations. The learning rate is 1 and the momentum is 0.8. Optimization for the flight took ~100 seconds. 

There is some left right flipping. At this point I'm not sure if the results are not good because the liftnet results are not good. The vector directions of my estimation seem to be matching the liftnet vector directions (though not perfectly.) I will have to improve my openpose results to improve the liftnet results and for that I need more scales. 


![small_video](https://senakicir.ams3.digitaloceanspaces.com/drone/2018-08-09-11-59_lift_res.mp4)
![small_video](https://senakicir.ams3.digitaloceanspaces.com/drone/2018-08-09-11-59_pose3d.mp4)


Things to do:
1. Try scipy.optimize.least_squares with LM. (maybe just use an approx to find jac)
2. Use pytorch to find the gradient, pass to scipy LM.
3. Make openpose work with larger images by tweaking with the code
