---
layout: post
title:  "August 7-8 Progress"
date:   2018-08-08 16:24:58 +0200
categories: progress
---

Hi!

Here are the results after I stopped subtracting the minimum z value of the human when normalizing for the height.
i.e. before:
```python
result = (relative_pos - min_z)/(max_z - min_z)
```
now:
```python
result = (relative_pos)/(max_z - min_z)
```

When I make the weight of the lift energy very large (=1), the Liftnet results and the normalized relative estimation results overlap as you expected. 

![small_video]({{ "/assets/progress_videos/2018-08-07-15-47_lift_res.mp4" | absolute_url }})

However, the overall result is not good.

![small_video]({{ "/assets/progress_videos/2018-08-07-15-47_plot3d.mp4" | absolute_url }})

When I make the weights normal however ({'proj': 0.006, 'smooth': 0.496, 'bone': 0.186, 'lift': 0.310} the overall result is still not very good and the relative estimation and Liftnet results do not match. 
Liftnet vs result (relative):
![small_video]({{ "/assets/progress_videos/2018-08-07-17-05_lift_res.mp4" | absolute_url }})
Overall results:
![small_video]({{ "/assets/progress_videos/2018-08-07-17-05_plot3d.mp4" | absolute_url }})
The losses look like this:
![small_video]({{ "/assets/progress_videos/2018-08-07-17-05_loss_53.png" | absolute_url }})

I've also tried comparing the bone vector directions of my estimation and Liftnet. However, this optimization takes longer (it was already taking long anyway :P) I think the relative estimation vs Liftnet results are already looking better. 
![small_video]({{ "/assets/progress_videos/2018-08-08-16-06_lift_res.mp4" | absolute_url }})
The overall estimation as well. 
![small_video]({{ "/assets/progress_videos/2018-08-08-16-06_plot3d.mp4" | absolute_url }})

However, unfortunately, after a while I get NaN results and the optimization is stopped. I'm playing around with different energy weights but I'm not sure what the problem is. 

Here are the losses at frames 44 and 52 respectively:
![small_video]({{ "/assets/progress_videos/2018-08-08-16-06_loss_44.png" | absolute_url }})
![small_video]({{ "/assets/progress_videos/2018-08-08-16-06_loss_52.png" | absolute_url }})
