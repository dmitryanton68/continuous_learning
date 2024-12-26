# __Continuous learning of spiking networks trained with local rules__
The code illustrates the results published in the article [_Continuous learning of spiking networks trained with local rules_](https://www.sciencedirect.com/science/article/abs/pii/S0893608022003379) in _Neural Networks_.
***
### ARTICLE:   
Antonov, D.I., Sviatov, K.V., Sukhov, S. Continuous learning of spiking networks trained with local rules. Neural Networks, Vol. 155, 2022, pp. 512-522, https://doi.org/10.1016/j.neunet.2022.09.003.
***
Abstract: Artificial neural networks (ANNs) experience catastrophic forgetting (CF) during sequential learning. In contrast, the brain can learn continuously without any signs of catastrophic forgetting. Spiking neural networks (SNNs) are the next generation of ANNs with many features borrowed from biological neural networks. Thus, SNNs potentially promise better resilience to CF. In this paper, we study the susceptibility of SNNs to CF and test several biologically inspired methods for mitigating catastrophic forgetting. SNNs are trained with biologically plausible local training rules based on spike-timing-dependent plasticity (STDP). Local training prohibits the direct use of CF prevention methods based on gradients of a global loss function. We developed and tested the method to determine the importance of synapses (weights) based on stochastic Langevin dynamics without the need for the gradients. Several other methods of catastrophic forgetting prevention adapted from analog neural networks were tested as well. The experiments were performed on freely available datasets in the SpykeTorch environment.
***
__The code is written in Python 3.8 using the [SpykeTorch](https://github.com/miladmozafari/SpykeTorch) framework__
***
The Python files in this repository correspond to the experiments described in the paper.
Spiking neural network (SNN) was trained on Task 1 (images of digits MNIST) till reaching the classification accuracy of ≈93%. After that, the network was trained on Task 2 (images of Latin letters EMNIST) over 100 epochs. During training on Task 2, we tested several methods to prevent the catastrophic forgetting of Task 1 (see the article for details). Figure shows the result of this training.  

![graphs](graphs.svg)   

__Figure:__ The accuracy of SNN in incremental domain learning experiments.     
Different panels show the efficiency of different methods for catastrophic forgetting prevention:    
(a) Catastrophic forgetting,    
(b) Lateral inhibition,     
(c) Pseudo-rehearsal,     
(d) Few-short self-remainder (0.25% stored samples),     
(e) Few-short self-remainder (10% stored samples),     
(f) Noise regularization,     
(g) Frozen large weights,     
(h) Langevin dynamics,     
(i) Joint training.    
Lines represent the mean; the shaded areas show the standard deviation. Dotted red lines show the recognition accuracy on Task 1; solid blue lines show the recognition test accuracy on Task 2; dashed cyan lines show the recognition accuracy of the training dataset of Task 2.
***
***
