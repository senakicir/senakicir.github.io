---
layout: blank
---

<h1 style="text-align: center;"> 3D Pose Based Feedback for Physical Exercises </h1>

<h2 style="text-align: center;"><a class="page-link" href="https://www.linkedin.com/in/ziyi-zhao-597026234/?trk=people-guest_people_search-card&originalSubdomain=ch">Ziyi Zhao</a><sup>1</sup>,<a class="page-link" href="https://senakicir.github.io/">Sena Kiciroglu</a><sup>1</sup>,<a class="page-link" href="https://www.linkedin.com/in/hugues-vinzant/?originalSubdomain=ch">Hugues Vinzant</a><sup>2</sup>,<a class="page-link" href="https://www.linkedin.com/in/yuan-cheng-a1344220b/">Yuan Cheng</a><sup>2</sup>,</h2>
<h2 style="text-align: center;"><a class="page-link" href="https://datascience.ch/team_member/isinsu-katircioglu/">Isinsu Katircioglu</a><sup>2</sup>, <a class="page-link" href="https://people.epfl.ch/mathieu.salzmann">Mathieu Salzmann</a><sup>1,3</sup>, <a class="page-link" href="https://people.epfl.ch/pascal.fua/bio?lang=en">Pascal Fua</a><sup>1</sup></h2>

<h3 style="text-align: center;"> 
<sup>1</sup> CVLab, EPFL, Switzerland <br>
<sup>2</sup> Former students of CVLab, EPFL, Switzerland <br>
<sup>3</sup> Clearspace, Switzerland </h3>

<div class="centered_div big">

<div class="div_sidebyside"><img src="https://lh4.googleusercontent.com/7uTSvpyjHR-PdHWJzORYi2VZIsv1D5H4Ocnswk0zVJ8P7n5xc-c6KGNUQRN6ni8dNGA=w2400"></div>
<div class="div_sidebyside"><img src="https://lh6.googleusercontent.com/8u5qOkDzExfHNz5YS-AInl5nVgMNgngcU0S-wM0wkEOGXsmQKQo3kSqq2HEA2-Hdfv8=w2400"></div>
</div>

<div class="centered_div big" style="padding-top:25px;">
<div class="div_rounded_corners"><a href="https://arxiv.org/abs/2208.03257" style="color: #fdfdfd;">arXiv</a></div>
<div class="div_rounded_corners"><a href="" style="color: #fdfdfd;">Code</a></div>
<div class="div_rounded_corners"><a href="https://youtu.be/W3kyyeHe0SI" style="color: #fdfdfd;">Video</a></div>
</div>

<img src="https://lh5.googleusercontent.com/q0b0XdYewFq0hW48HzMSe0drh7QMqCqSL3H-qGMjt_XkeARnYgAVpki2d5d7y-5myN0=w2400" style="display:block; margin:auto; width: 85%; max-width: 85%; height:auto;">

<div class="div_text">
<h1 style="text-align: center;">Abstract</h1>
Unsupervised self-rehabilitation exercises and physical training can cause serious injuries if performed incorrectly. We introduce a learning-based framework that identifies the mistakes made by a user and proposes corrective measures for easier and safer individual training. Our framework does not rely on hard-coded, heuristic rules. Instead, it learns them from data, which facilitates its adaptation to specific user needs. To this end, we use a Graph Convolutional Network (GCN) architecture acting on the user's pose sequence to model the relationship between the body joints trajectories. To evaluate our approach, we introduce a dataset with 3 different physical exercises. Our approach yields 90.9% mistake identification accuracy and successfully corrects 94.2% of the mistakes.
</div>

<hr class="hr_style">

<div class="div_text div_gray">
<div style="width: 100%; display:inline-block;">
<h3> Exercise Feedback </h3>

</div>Being able to perform exercises without requiring the supervision of a physical trainer is a convenience many people enjoy, however unsupervised self-rehabilitation exercises and physical training can cause serious injuries if performed incorrectly. We aim to use deep learning to recognize the type of incorrect exercise being performed, and give a personalized 3D pose sequence based correction. To the best of our knowledge, our framework is the first to both identify mistakes and suggest personalized corrections to the user.
</div>

<div class="div_text div_gray">
<h3> Framework </h3>

<div style="width: 80%; display:block; margin:auto; padding-bottom:2px;"><img style="margin:5px; border-radius:10px;" src="https://lh6.googleusercontent.com/2PO6dkMio3BkXFS64kEFeesOmkrTeE4Wyjbf5BVIejP_87fwuKDZNHDyvvBPhUR6vyU=w2400"></div>
<div style="width: 100%; display:inline-block;">
Our framework for providing exercise feedback relies on GCNs which can learn to exploit the relationships between the trajectories of individual joints. The overall model consists of two branches: <b>the classification branch</b> which predicts whether the input motion is correct or incorrect, specifying the mistake being made in the latter case, and <b>the correction branch</b> that outputs a corrected 3D pose sequence, providing a detailed feedback to the user. 
We feed the predicted action labels coming from the classification branch to the correction branch, which is called the “feedback module”. It allows us to explicitly provide label information to the correction module, enabling us to further improve the accuracy of the corrected motion.
</div>
</div>


<div class="div_text div_gray">
<div class="div_aligned">
<div style="width: 60%; display:inline-block; vertical-align:middle;"><img style="margin:1px; width:95%;border-radius:10px;" src="https://lh5.googleusercontent.com/D7t5OKOhRk7U8TfiPjM4lY-mlZI4lbI0mr31nWcr4mi-J6AybxvkiJC5lV8guyJ8QYo=w2400"> </div>
<div style="width: 40%; display:inline-block;"> 
<h3 style="text-align: right;"> EC3D Dataset</h3>

To showcase our framework’s performance, we recorded a physical exercise dataset with 3D poses and instruction label annotations.  Our dataset features 3 types of exercises; squats, lunges and planks. Each exercise type is performed correctly and with mistakes following specific instructions by 4 different subjects. We use the EC3D dataset to evaluate our model performance both quantitatively and qualitatively.

</div>
</div>
</div>

<h3> BibTeX </h3>
  If you find our work useful, please cite it as:

    @inproceedings{zhao2022exercise,
      author = {Zhao, Ziyi and Kiciroglu, Sena and Vinzant, Hugues and Cheng, Yuan and Katircioglu, Isinsu and Salzmann, Mathieu and Fua, Pascal},
      booktitle = {ACCV},
      title = {3D Pose Based Feedback for Physical Exercises},
      year = {2022}
    }