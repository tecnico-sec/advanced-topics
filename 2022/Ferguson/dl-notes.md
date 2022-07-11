# Paper Notes
Title: Examining the Efficacy of Decoy-based and
Psychological Cyber Deception

Authors: Kimberly J. Ferguson-Walter, Maxine M. Major, Chelsea K. Johnson, and Daniel H. Muhleman

Reviewer: DL

Link: https://www.usenix.org/system/files/sec21-ferguson-walter.pdf


## Contribution
The recent increase in cyber attacks motivates the creation of better defensive techniques. Attackers rely on the observation of the environment, such as the characteristics of a network, to carry out their attacks. One possible way to mitigate this is to hinder the attacker's perception of the environment, through techniques such as deception, where the attacker is provided with wrong information about the environment's characteristics.

The authors simulated a network with exploitable machines and low-interaction decoy machines, gathered a group of professionals that act as cyber attackers, and split them into 4 groups with different experimental conditions encompassing the existence or not of decoy machines and the awareness or not of the decoy machines in the network. The results obtained are interpreted to infer the effect that the experimental conditions have on the attackers' ability to exploit the machines so that deception techniques can be used to prevent attackers from successfully compromising cyber environments.


## Strengths
* A wide number of factors and resources are taken into account when measuring the success of an attacker. The authors don't only measure success, but they do it following several stages (Cyber Kill Chain model) which allow a better understanding of the implications of using decoys.

* Most techniques and conclusions sit on top of extensive research published in important conferences and all results are analyzed in detail.

* Each hypothesis is thoroughly put against the obtained results in section 7.

* Good assessment of the study limitations and future work on Sections 7.1 and 8.


## Weaknesses
* Despite the difficulty in finding adequate candidates for this study, 123 professionals divided into 4 different experimental setups, with unequal participant numbers for each category (35 for AU, 28 for AI, 30 for PU, and 30 for PI) was not enough to infer relevant conclusions. In the results presented in Table 2, Figure 1, and Figure 2, the differences obtained for each experimental setup are not that significant and may have happened by chance.

* The decoy machines do not present realistic behavior and it has been demonstrated, for instance, in the paper "Towards a Believable Decoy System: Replaying Network Activities from Real System" that there are multiple deception evasion attacks that can help attackers detect decoy machines with high accuracy. It would be more relevant to see a study where decoy machines were on pair with the state-of-the-art.

* Even though decoy systems are becoming increasingly important in preventing and detecting cyber attacks, the psychological influence that knowing their existence or not has on attackers does not seem like a relevant enough factor when compared to their actual potential in detecting attack attempts.

* The results taken from the study were subjected to a lot of manual analysis and there is no objective way to define whether an attack was successful or not. This is inferred from a set of observations of the attackers' activities and their logs, which do not seem like fair criteria overall.

* Synthetic penetration testing is not realistic because attackers are less cautious about being detected.


## Points of interest
* Tularosa study: https://www.osti.gov/servlets/purl/1524844

* Detailed experimental conditions and results in the paper Appendix and https://cfwebprod.sandia.gov/cfdocs/CompResearch/docs/TularosaAppendix.pdf.


## See also
* Evolving from Honeypots to Active Deception Defenses: https://fidelissecurity.com/resource/video/evolving-honeypots-active-deception/

* Deception Game on Decoy Systems: https://users.ece.cmu.edu/~gko/resources/talk_qual15.pptx

* Towards a Believable Decoy System: Replaying Network Activities from Real System: https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=9162163


## Comparison
* Despite my interest in psychological and social factors in security, I did not find this work relatable or complementary to my research.


# Questions
1. Is there any difference between the decoy machines used in the study and honeypots? Do you think that the experimental setup represents a realistic scenario of how decoy systems are used to improve security?

2. Why do you think that the decoy machines being low-interaction and not revealing realistic behavior did not seem to affect the study's results?

3. Do you think that the authors could have simplified the detection of successful attacks, for instance by simplifying the experimental setup to a CTF challenge or by using Intrusion Detection Systems? Why didn't the authors opt for these solutions?

4. Is keystroke count a good measure to infer an attacker's success?