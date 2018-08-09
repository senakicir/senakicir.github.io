---
layout: post
title:  "August 9 Progress"
date:   2018-08-09 14:24:58 +0200
categories: progress
---

Following Helge's suggestion, I added a small number to the denominator of a division operation to avoid dividing by 0 (or a very small number). This solved my NaN problem from yesterday!

Here is another experiment with weights: {'proj': 0.0066, 'smooth': 0.53, 'bone': 0.199, 'lift': 0.265} and 4000 iterations. The learning rate is 1 and the momentum is 0.8. Optimization for the flight took ~100 seconds. 

There is some left right flipping. At this point I'm not sure if the results are not good because the liftnet results are not good. The vector directions of my estimation seem to be matching the liftnet vector directions (though not perfectly.) I will have to improve my openpose results to improve the liftnet results and for that I need more scales. 

Liftnet vs normalized estimation:
![small_video](https://senakicir.ams3.digitaloceanspaces.com/drone/2018-08-09-11-59_lift_res.mp4)
Overall result:
![small_video](https://senakicir.ams3.digitaloceanspaces.com/drone/2018-08-09-11-59_plot3d.mp4)

On another note, Semih found a minimizer in Scipy that implements LM! It's scipy.optimize.least_squares. However, when I try to use it I get the error (ValueError: Method 'lm' doesn't work when the number of residuals is less than the number of variables.) This is because my function returns a single value as the loss (sum of all my loss terms for all the frames in my window) instead of a vector of residuals.(TODO: return residuals also)

Therefore, first instead of changing my function, I used the trf method (Trust Region Reflective algorithm). I'm also using the 2-point approximation method to find the jacobian (TODO: find jacobian via pytorch). This method works very quickly during calibration mode (~2 seconds of computation time vs ~15 seconds from pytorch's SGD), however it's varies in flight mode (varying between ~300 seconds and 18 seconds.) As for the results, in calibration mode they are the same but in flight mode they are better (still don't expect too much).

Here are some results, stay tuned for more! 
![small_video](https://senakicir.ams3.digitaloceanspaces.com/drone/2018-08-09-15-00_plot3d.mp4)

--- 
Update:

I've implemented LM! It is much faster (calibration around 1.7 seconds, flight varying between 150 and 22 seconds). It also gives a lower error value after calibration. I can't tell if the flight performance is good or not. 

Results:
![small_video](https://senakicir.ams3.digitaloceanspaces.com/drone/2018-08-09-19-41_plot3d.mp4)
Some pretty bizarre looking loss visualizations:
![small_video](https://senakicir.ams3.digitaloceanspaces.com/drone/2018-08-09-19-41_loss_81.mp4)

One problem: The scipy documentation states "**Method ‘lm’ always uses the ‘2-point’ scheme.'**" This seems I cannot find the jacobian using pytorch and pass it to scipy (instead of 2 point approximation.) like I planned on doing. What should I do? I can still try passing the jacobian to scipy and use trf instead of LM.

Things to do:
1. Find jac with pytorch, pass to numpy (find jacobian somehow instead of approximating)
2. Make openpose work with larger images by tweaking with the code
