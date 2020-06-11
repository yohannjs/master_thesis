# Guide to literature used in thesis, and summaries of individual articles.
This document is meant to be a guide to all the literature used by the author of the master thesis. 
The document is divided into sections for the different types of literetaure. I.e. separate sections for literature on ultrasound technology, statistical methods and machine learning
Each document is linked to, with a name which is meant to give a basic description of the document.

## Ultrasound imaging and echocardiography
* [X] [Nice page about heart](https://www.medicalnewstoday.com/articles/320565.php#how-the-heart-works)
* [X] [Basics ultrasound](http://folk.ntnu.no/stoylen/strainrate/Basic_ultrasound)
* [X] [Strain rate imaging (Asbjørn Støylen homepage)](http://folk.ntnu.no/stoylen/strainrate/index.html)
* [X] [Strain rate imaging (Asbjørn Støylen thesis intro)](http://folk.ntnu.no/stoylen/strainrate/thesis_AS.pdf)
* [ ] [Echocardiography book norwegian](https://bitbucket.org/ntnuultrasoundgroup/msc_yohann_sandvik/src/master/literature/Kardiologiske%20metoder%20-%20Kardiologisk%20ultralyddiagnostikk.pdf)
* [ ] [Myocardial Imaging book](https://bitbucket.org/ntnuultrasoundgroup/msc_yohann_sandvik/src/master/literature/Myocardial%20imaging%20-%20tissue%20Doppler%20and%20speckle%20tracking.pdf)
* [ ] [Page about blood pressure](https://www.heart.org/en/health-topics/high-blood-pressure/understanding-blood-pressure-readings)

# Summaries of individual papers, and other sources

## Characterization of myocardial motion patterns by unsupervised multiple kernel learning
#### Authors
Sergio Sanchez-Martinez, Nicolas Duchateau, Tamas Erdei, Alan G. Fraser, Bart H. Bijnens, Gemma Piella
#### Abstract
We propose an independent objective method to characterize different patterns of functional responses
to stress in the heart failure with preserved ejection fraction (HFPEF) syndrome by combining multiple
temporally-aligned myocardial velocity traces at rest and during exercise, together with temporal infor-
mation on the occurrence of cardiac events (valves openings/closures and atrial activation). The method
builds upon multiple kernel learning, a machine learning technique that allows the combination of data
of different nature and the reduction of their dimensionality towards a meaningful representation (out-
put space). The learning process is kept unsupervised, to study the variability of the input traces without
being conditioned by data labels. To enhance the physiological interpretation of the output space, the
variability that it encodes is analyzed in the space of input signals after reconstructing the velocity traces
via multiscale kernel regression. The methodology was applied to 2D sequences from a stress echocardio-
graphy protocol from 55 subjects (22 healthy, 19 HFPEF and 14 breathless subjects). The results confirm
that characterization of the myocardial functional response to stress in the HFPEF syndrome may be im-
proved by the joint analysis of multiple relevant features.

#### Notes
* Study includes 55 subjects (22 healthy, 10 HFPEF and 14 breathless).
* They extract a total of 4 velocity curves from the 4CH view, ultrasound video of each patient: base septal/lateral at rest/submaximal.
* The 4 velocity curves included as input features, in addition each velocity curve is split into 5 segments (iso-volumic contraction, systole, iso-volumic relaxation, early and late diastole) making up another 20 curves per patient, which are also included as input features. They also use scalar parameters (such as E/e' ratio) as input features.
* The total number of features isn't given explicitly I think...
* The method consists of two steps (each with substeps):
    1. Multiple kernel learning (MKL) to find the optimal combination of input features, and maps each subject to a space of reduced dimensions.
        * An affinity matrix for each feature is created based on the M (#patients) samples of each feature. A global affinity matrix is also created, which is the sum of the preceding affinity matrices.
        * MKL optimization for optimal feature combination selection.
        * Input mapped to output space of reduced dimensions.
    2. Input signals are reconstructed using multiscale kernel regression.

#### Biblatex reference
```
@article{Sanchez-MartinezSergio2017Comm,
    issn      = {1361-8415},
    journal   = {Medical Image Analysis},
    pages     = {70--82},
    volume    = {35},
    publisher = {Elsevier B.V},
    number    = {C},
    year      = {2017},
    title     = {Characterization of myocardial motion patterns by unsupervised multiple kernel learning},
    language  = {English},
    author    = {Sanchez-Martinez, Sergio and Duchateau, Nicolas and Erdei, Tamas and Fraser, Alan G and Bijnens, Bart H and Piella, Gemma},
    keywords  = {Myocardial Motion ; Echocardiography ; Multiple Kernel Learning ; Pattern Analysis ; Myocardial Motion ; Echocardiography ; Multiple Kernel Learning ; Pattern Analysis ; Medicine ; Engineering},
}
```
