layout: misc
---

# Long Term Motion Prediction Using Keyposes

### <a class="page-link" href="https://senakicir.github.io/">Sena Kiciroglu</a>, <a class="page-link" href="https://weiwangtrento.github.io/">Wei Wang</a>, <a class="page-link" href="https://people.epfl.ch/mathieu.salzmann">Mathieu Salzmann</a>, <a class="page-link" href="https://people.epfl.ch/pascal.fua/bio?lang=en">Pascal Fua</a> 

### CVLab, EPFL, Switzerland
### MHUG, University of Trento, Italy
### Clearspace, Switzerland

<img src="https://drive.google.com/uc?id=1qIRO07U7fpo4Nq-y89v8SJa2M4UxLQ6-" style="width: 50%; max-width: 50%; height: auto;">

## <a href="https://arxiv.org/pdf/2012.04731.pdf">arXiv</a><a href="">Code</a>

<img src="https://drive.google.com/uc?id=1oWueDaacF4dF5owvFhP_-Qn3A9Yp0KIy" style="width: 100%; max-width: 100%; height: auto;">

## Abstract

Long term human motion prediction is essential in safety-critical applications such as human-robot interaction and autonomous driving. In this paper we show that to achieve long term forecasting, predicting human pose at every time instant is unnecessary. Instead, it is more effective to predict a few keyposes and approximate intermediate ones by interpolating the keyposes. 

We demonstrate that our approach enables us to predict realistic motions for up to 5 seconds in the future, which is far longer than the typical 1 second encountered in the literature. Furthermore, because we model future keyposes probabilistically, we can generate multiple plausible future motions by sampling at inference time. Over this extended time period, our predictions are more realistic, more diverse and better preserve the motion dynamics than those state-of-the-art methods yield.

### Long Term Motion Prediction

Motion prediction is an essential component in safety-critical applications, such as human-robot interaction and autonomous driving. Most existing methods have accurate pose predictions of up to 1 second. Our work extends this time horizon to 5 seconds, by following a different approach. Instead of regressing a pose at every future timestep, we aim to predict the next "keypose" in the sequence via a classification scheme.

### Keyposes

Human motion follows patterns that are well-represented by a few essential poses in the sequence. We call such poses ``keyposes". By interpolating between the keyposes, we can reconstruct the original sequence. Therefore, it is sufficient to only predict the keyposes in the sequence. We extract the keyposes by determining the poses which yield minimum L2 error when used to reconstruct the original sequence.


## BibTeX
  If you find our work useful, please cite it as:
  
    @inproceedings{kiciroglu2022keyposes,
      author = {Kiciroglu, Sena and Wang, Wei and Salzmann, Mathieu and Fua, Pascal},
      booktitle = {3DV},
      title = {Long Term Motion Prediction Using Keyposes},
      year = {2022}
    }