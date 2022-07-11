# Comments on _paper-3_

Title: _Examining the Efficacy of Decoy-based and Psychological Cyber Deception_

Authors: _Kimberly J. Ferguson-Walter, Maxine M. Major, Chelsea K. Johnson, Daniel H. Muhleman_

Reviewer: _MF_

[Link to publication page](https://www.usenix.org/system/files/sec21-ferguson-walter.pdf)

## Contribution

This paper investigates the effectiveness of using decoy systems for cyber defense and the impact of informing attackers of its existence in the cyber attack behavior.
The authors analyze data provided from the Tularosa study, in which professional red teamers performed network penetration tests in a controlled environment to analyze the influence of both cyber deceptions and cyber psychology in anticipating or delaying cyber attacks.
They validate three out of four proposed hypotheses, namely, that deceptive tools reduce the effectiveness of the attack, even if information on deception is provided to the attacker and that cyber and psychological deception affected the cognitive and emotional state of the attackers, who showed decision-making biases.


### Strengths

This paper investigates the theory that deceptive defenses can help to anticipate or delay cyber attacks.
A strong point of this work is that it provides empirical evidence that employing cyber deception and cyberpsychology-based techniques influences human behavior, which affects decision making. This shows that innovative strategies that do not rely on practical security sound-proofing measures can improve the security of systems.
Another strong point of this work is the methodology applied to overcome the challenge of measuring the success of the attack. The authors employed an extensive set of metrics, curated for the specific use case of this paper, where each was able to provide meaningful insights.


### Weaknesses

The experimental settings related to the decoy systems lacked some technical details. It is stated that the decoys respond to scans almost the same as their real counterparts but did not respond to other activities such as exploits, which seems a bit vague. I think this non-responsive behavior should be better characterized, since it may have impact on the attackers' decision making - is it a silent fault? what is the output of non supported commands?
On the same note, the description of the dataset analysis also lacks technical details and a proper evaluation, which raises some issues about the validity of the data, e.g., how was the search for keywords performed on keylog data? Can false negatives/positives result from this analysis? 
Concerning the statistical results, the authors do not explain the statistical notation (e.g. what is the H(x), what is a good p?), so it becomes harder to analyze the quality of the results.
The authors perform a security assessment, based on the end-of-day reports of the participants, which is manually labeled. However, in some cases, the percentage of Not Applicable cases is superior the the Applicable (Secure/Insecure label), which I believe leads to inconclusive results. Furthermore, they do not explain what they consider to be "not applicable".


### Points of interest

The conclusions of this work may help future researchers to discover more technical solutions based on deceptive strategies that trigger decision-making bias.

### Questions for discussion

1. What would change if the attackers had consequences on an unsuccessful attack?
2. How does the number of decoy systems influence the results? In this case we have a 50/50 ratio but this may be unfeasible to the defender.
3. Why does a decrease in IDS alerts demonstrates a decrease in forward progress? Can't the attack just be more efficient?

## Comparison

Since I work with cyber security, this work is very relevant and it helped me to be open to more innovative strategies that do not rely on security walls.