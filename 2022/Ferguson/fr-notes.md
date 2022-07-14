# Comments on paper-3

Title: Examining the Efficacy of Decoy-based and Psychological Cyber Deception

Authors: Kimberly J. Ferguson-Walter, Maxine M. Major, Chelsea K. Johnson, Daniel H. Muhleman

Reviewer: FR

[Link to publication page](https://www.usenix.org/system/files/sec21-ferguson-walter.pdf)

## Contribution

Understanding cyber attackers' operations is an important step toward robust cyber defense techniques. Previous works focused solely on qualitative data while attempting to fill this gap in computer security research. This work seeks to leverage quantitative cyber task data to understand cyber attackers better.

In order to conduct their research, the authors focused on the psychological and technological impact of deception techniques to both delay and deterred possible attacks, regardless of whether the attackers were aware of the defensive countermeasures. The goal is to use this study further to develop state-of-the-art mitigation methods that leverage human decision-making limitations and thus thwart cyber attackers.

The main contribution of this paper is achieved through evaluating the data collected in the Tularosa Study, conducted with expert human subjects, whilst focusing on the efficacy of decoy systems and psychological deception. 

### Strengths

- The study where the data was obtained, Tularosa, contained vast amounts of data that wasn’t previously analyzed with the same purpose of this work. Obtaining such data would be very difficult due to the setup involved, ranging from participants to network. Leveraging the data for this study was a solid decision.
- Very expansive results, ranging from technical exploits such as the EternalBlue exploit and target selection through Metasploit to altered perception analysis (e.g., psychological deception and decay interactions). The latter is the main focus of this work.


### Weaknesses

- There are various points in the paper where statistical terms are introduced without placing them into the context of the problem. However, there are other points in the paper where it is done; there seems to be no consistency.
- While the study is pervasive, it has very little technological detail. Specific exploits are mentioned, but there is no explanation regarding the technologies used for deception. It could be interesting to see if state-of-the-art technology was used to improve defensive countermeasures further.


### Points of interest

An interesting result is that decoy techniques seem more effective when the attacker is aware of their existence. This claim is supported by the results present in the paper. Furthermore, there is also presented evidence that certain attackers may struggle to deal with decoy countermeasures and proceed with less caution; this approach can further aid faster detection and mitigation. It was also shown that the look for decoys led to significant amounts of wasted resources by the attackers.

The data was collected in a system where an Intrusion Detection System (IDS) was not present in the network. An interesting study would be to perform a similar experiment in which common network defenses are also in place, such as an IDS. Experts estimate that about 80% of threats can be stopped through said systems (see link below). In this work, deception is evaluated as a stand-alone component nearly (see Q1).


### Questions for discussion

Q1: How would the results change in the presence of an entire network, for example, with an active IDS and with real attackers that were further motivated to hide their exploits? Would deception still be as effective?

Q2: Honeypots are a common approach to detecting attackers; how do they differ from deception technology? Or would honeypots be classified as deception technology?

Q3: What would be the advantages of using deception technology in the real world? Detecting attackers before a breach, eliminating false positives, scales with network size, orthogonal to network functionality, and real-time network threat analysis.


## See also

- [Deception technology](https://www.countercraftsec.com/deception-technology.html#separator-questions)

## Comparison

This publication is entirely out of the scope of my research work as I focus on distributed systems and data partitioning.
