# Comments on P3

Title: Examining the Efficacy of Decoy-based and Psychological Cyber Deception

Authors: Kimberly J. Ferguson-Walter, Maxine M. Major, Chelsea K. Johnson, Daniel H. Muhleman

Reviewer: RS

[Link to publication page](https://www.usenix.org/system/files/sec21-ferguson-walter.pdf)

## Contribution

Cyber deception, a technique to inject false beliefs into cyber attackers to delay, deter and disrupt attacks, has been growing in popularity. However, there is still a lack of studies on its efficacy and impact. This work analyzes the effectiveness of two cyber deception techniques: decoys, which introduce false targets in a network to waste attacker resources, and cyberpsychology, by giving information about possible decoys that may or may not exist.

The main contribution of this work is an in-depth analysis of cyber deception techniques using a real-world experiment, investigating multiple hypotheses, most notably:
* If defensive cyber tools and psychological deception impede attackers who seek to penetrate computer systems and exfiltrate information;
* If defensive deception tools are practical even if an attacker is aware of their use.

### Strengths

* Wide and complete range of obtained data, both qualitative and quantitative.
* a Great number of participants for a realistic statistical analysis, including realistic backing of the author's hypothesis. 

### Weaknesses

* There is a lack of comparison between the delay of forwarding progress and the cost of setting and maintaining the decoy nodes. 

* There is no general forward progress metric, i.e., the actual total progress is done by each group or how this metric evolved over time. 

* The differences in the network between the Present and Absent environments do not lead to a fair comparison. Factors such as different network sizes and lack of "faulty" nodes on the Absent side induce different behaviors and strategies by the participants.

* Some essential metrics are heavily affected by the lack of real-world consequences, specifically regarding the Present-Informed group.

### Points of interest

- The test environment used was complete and flexible in terms of obtained information/statistics and a wide range of attack vectors for attackers to follow. Some real-world consequences (compensation penalization for lack of stealthiness) would enrich the study.

- The psychological impact of deception in Absent-Informed scenarios brings surprisingly effective and exciting results. A deeper study of these psychological effects in cybersecurity should come into consideration. 

### Questions for discussion

1. Would you consider the decoy's effect on forwarding progress to lose effectiveness over time or be a constant decrement in exploitation
2. Would you consider the effect of decoys worth their cost? 
3. If real-world stakes were present, how would you predict it would skew the results?

## See also

- [The Tularosa Study: An Experimental Design and Implementation to Quantify the Effectiveness of Cyber Deception](https://www.researchgate.net/publication/330324907_The_Tularosa_Study_An_Experimental_Design_and_Implementation_to_Quantify_the_Effectiveness_of_Cyber_Deception)
- [Friend or Faux: Deception for Cyber Defense](https://www.jstor.org/stable/26502755?seq=1)

## Comparison

While this work has little to do with my own, it brings exciting questions on how the psychological effect of systems can affect both users and developers. It would be interesting to study how the usage of different consistency levels for applications affects developers' perception of application/code complexity.  
