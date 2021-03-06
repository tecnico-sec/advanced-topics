# Comments on _paper-3_

Title: _Online Website Fingerprinting: Evaluating Website Fingerprinting Attacks on Tor in the Real World_

Authors: _Giovanni Cherubin, Rob Jansen, Carmela Troncoso_

Reviewer: _MF_

[Link to publication page](https://www.usenix.org/system/files/sec22summer_cherubin.pdf)

## Contribution

This paper analyzes the effectiveness of website fingerprinting (WF) attacks to break unlikability and enable deanonymization using real-world Tor traffic. The authors investigate the limitations of traditional Tor WF attacks and show that they are based on unrealistic assumptions, such as synthetic traffic generation and concept drift, which decreases the chances of a successful attack in the real world - <60% accuracy when monitoring 100 websites. They evaluate the efficacy of both attack models (traditional vs. using genuine data) and show that the latter performs significantly better in the real world.


### Strengths

This paper investigates a novel threat model, which is based on collecting real traffic at exit relays, contrary to previous researched models.

* A strong point of this work is that the new approach trains and tests models with genuine data instead of relying on synthetic data that may not depict real-world interactions with the Tor network. The authors evaluate not only the novel threat model but also the existing limitations of traditional models.

* Another strong point is the combination set of the phases used in the evaluation (e.g., dataset, relays for training, and evaluation), which provided meaningful insights.

### Weaknesses

* The authors evaluate the synthetic results with a dataset generated by them, which only samples 1k URLs out of 144k from previous research. They also state (Section 6.2) that the choice of monitored websites influences WF's performance. I believe that they should have evaluated with closer settings to the previous research to be a more fair comparison (e.g., similar and/or improved dataset). 
  
* The authors motivate their work with the limitations of using synthetic traffic. However, they evaluate the attacks with genuine data, combined with the new threat model, which they state would not be used by a real adversary (5.2 - Phase III) and s not characteristic of WF (Introduction). I believe the paper lacks more detailed discrimination of the results, showing that only an improved model (e.g., from collecting larger datasets or improving browsing models) would still have the same (or similar) limitations.

* Figure 11 shows a comparable (medium) performance of Exit-Exit and Entry-Entry, with an average of ~50% accuracy. This result may indicate no difference when training a model using real vs. synthetic traffic to real-world attacks, and the authors do not discuss it.
  
* The authors state that an adversary can observe additional metadata when running an entry relay. However, they do not discuss whether this metadata could improve the accuracy of previous studies or be used in future work.


### Points of interest

The novel threat model can open new exciting lines of research.

### Questions for discussion

1. How feasible would the attacks be based on the new model in the real world?
2. How could researchers improve synthetic datasets to train better models? Would it be enough?
3. The authors only evaluate the false negative rate. Concerning the real implications of attacks, do you think FN is worse than FP?

## Comparison

Although there is a fantastic body of work done on website fingerprinting attacks on Tor, this paper provided a different approach and an innovative point of view of the problem, which helped me to understand the need to think outside of the box. I believe this will help my research as I search for new topics.
