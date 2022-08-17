---
layout: blank
---

<h1 style="text-align: center;"> Long Term Motion Prediction Using Keyposes </h1>

<h2 style="text-align: center;"><a class="page-link" href="https://senakicir.github.io/">Sena Kiciroglu</a>, <a class="page-link" href="https://weiwangtrento.github.io/">Wei Wang</a>, <a class="page-link" href="https://people.epfl.ch/mathieu.salzmann">Mathieu Salzmann</a>, <a class="page-link" href="https://people.epfl.ch/pascal.fua/bio?lang=en">Pascal Fua</a></h2>

<h3 style="text-align: center;"> 
CVLab, EPFL, Switzerland <br>
MHUG, University of Trento, Italy <br>
Clearspace, Switzerland </h3>

<div class="centered_div big">

<div class="div_sidebyside"><img src="https://drive.google.com/uc?id=1qIRO07U7fpo4Nq-y89v8SJa2M4UxLQ6-"></div>
<div class="div_sidebyside"><img src="https://drive.google.com/uc?id=1Yc_9t3vuAD3aqvDEV1yTNm6Np5rYyqoR"></div>
<div class="div_sidebyside"><img src="https://drive.google.com/uc?id=1SHHOqY1MH-x-Vdsj7GuDcAIaC0mZ-Zex"></div>
</div>

<div class="centered_div big" style="padding-top:25px;">
<div class="div_rounded_corners"><a href="https://arxiv.org/pdf/2012.04731.pdf" style="color: #fdfdfd;">arXiv</a></div>
<div class="div_rounded_corners"><a href="" style="color: #fdfdfd;">Code</a></div>
<div class="div_rounded_corners"><a href="" style="color: #fdfdfd;">Video</a></div>
</div>

<img src="https://drive.google.com/uc?id=101iZGLME9ajUCwd1SeWTHbITVrBZYuCy" style="display:block; margin:auto; width: 80%; max-width: 80%; height:auto;">

<div class="div_text">

<h1 style="text-align: center;">Abstract</h1>
Long term human motion prediction is essential in safety-critical applications such as human-robot interaction and autonomous driving. In this paper we show that to achieve long term forecasting, predicting human pose at every time instant is unnecessary. Instead, it is more effective to predict a few keyposes and approximate intermediate ones by interpolating the keyposes. <br><br>

We demonstrate that our approach enables us to predict realistic motions for up to 5 seconds in the future, which is far longer than the typical 1 second encountered in the literature. Furthermore, because we model future keyposes probabilistically, we can generate multiple plausible future motions by sampling at inference time. Over this extended time period, our predictions are more realistic, more diverse and better preserve the motion dynamics than those state-of-the-art methods yield.
</div>

<hr class="hr_style">

<div class="div_text div_gray">
<div style="width: 100%; display:inline-block;">
<h3> Long Term Motion Prediction </h3>

Motion prediction is an essential component in safety-critical applications, such as human-robot interaction and autonomous driving. Most existing methods have accurate pose predictions of up to 1 second. Our work extends this time horizon to <b>5 seconds</b>, by following a different approach. Instead of regressing a pose at every future timestep, we aim to predict the next "keypose" in the sequence via a classification scheme.</div>
</div>

<div class="div_text div_gray">
<h3> Keyposes </h3>

<div style="width: 80%; display:block; margin:auto; padding-bottom:2px;"><img style="margin:5px; border-radius:10px;" src="https://drive.google.com/uc?id=1oQIbFwesOnt41pKjlWRg26xMT_Yysy-F"></div>
<p class="fig_caption" style="width: 80%; padding-bottom:10px"> Figure: Distribution of keyposes in sequence. Plots show the x, y, and z coordinates of a single joint across time.</p>
<div style="width: 100%; display:inline-block;">
Human motion follows patterns that are well-represented by a <b>few essential poses</b> in the sequence. We call such poses "keyposes". By interpolating between the keyposes, we can reconstruct the original sequence. Therefore, it is sufficient to only predict the keyposes in the sequence. We extract the keyposes by determining the poses which yield <b>minimum L2 error</b> when used to reconstruct the original sequence.</div>
</div>

<div class="div_text div_gray">
<div class="div_aligned">
<div style="width: 35%; display:inline-block; vertical-align:middle;"><img style="margin:5px; width:85%;border-radius:10px;" src="https://drive.google.com/uc?id=1zFb-oKvE_qQZXzpb4yGBWGaTZHSqMsDy"> </div>
<div style="width: 65%; display:inline-block;"> 
<h3 style="text-align: right;"> Predicting Keyposes</h3>

We cluster and label the keyposes and turn motion prediction into a <b>classification</b> problem. This shifts the focus on the transition from one keypose label to another and avoid accumulating errors. We have designed a GRU based framework for keypose prediction. Moreover, by sampling the predicted logits during inference we can generate <b>diverse future motions</b>. 
</div>
</div>
</div>



<h3> BibTeX </h3>
  If you find our work useful, please cite it as:

    @inproceedings{kiciroglu2022keyposes,
      author = {Kiciroglu, Sena and Wang, Wei and Salzmann, Mathieu and Fua, Pascal},
      booktitle = {3DV},
      title = {Long Term Motion Prediction Using Keyposes},
      year = {2022}
    }