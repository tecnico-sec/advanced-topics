# Comments on _paper-6_

Title: _Back-Propagating System Dependency Impact for Attack Investigation_

Authors: _Pengcheng Fang, Peng Gao, Changlin Liu, Erman Ayday, Kangkook Jee, Ting Wang, Yanfang (Fanny) Ye, Zhuotao Liu and Xusheng Xiao_

Reviewer: _PO_

[Link to publication page](https://www.usenix.org/conference/usenixsecurity22/presentation/fang)

## Contribution

_What are the major issues addressed in this publication?_

- When a cyber attack occurs, experts rely on system monitoring tools to analyze the activities that led to a security breach. Causality analysis is performed over the collected logs in order to identify the attack entry point and its ramifications (e.g. other systems that got compromised). This causality analysis is performed over a system dependency graph where nodes represent system entities and edges represent system events. These graphs are huge and experts rely on solutions that are able to reduce their size in order to be able to more easily pinpoint what caused an attack. Current solutions have some downsides: rely on heuristics that can cause loss of information; or rely on execution profiles to detect anomaly events, which may have be unfeasible for enterprises with huge amount of systems dedicated for different tasks. Beside that, graphs should be as small as possible in order to facilitate the analysis, something that current solutions also fail.


_What are the main contributions?  (as stated by the authors)_

- Authors propose DepImpact, a tool that facilitates attack analysis by being able to identify critical edges and attack entries in large dependency graphs
- DepImpact is able to reduce dramatically a dependency graph while still preserving the information that led an attack to happen (critical path)
- DepImpact offers better performance compared to current state of the art


### Strengths

_In your opinion, what are the strengths of the publication?_

- Clear background on why system monitoring tools are important and their relation to causality analysis
- Shortcomings of previous work is addressed: PrioTracker and NoDoze they achieve poor performance and provide bigger graphs compared to DepImpact
- DepImpact was implemented and evaluated against known attacks/exploits (7 attacks from prior work's evaluation and a public dataset released by DARPA TC program)
- Evaluation clearly states the advantages of DepImpact compared to current state of the art: up to 72 times more effective in graph reduction without loss of information; ~70% improvememtn in ranking attack entries
- DepImpact does not rely on third-party services that flag malicious files or IP addresses



### Weaknesses

_In your opinion, what are the weak points in this publication?_

- In the evaluation the authors study the relation between number of entry nodes and FPR/FNR. The authors state that DepImpact should "stop choosing more entry nodes when including more entry node for forward analysis will result in a significant increase of the critical component" in order to have the best FPR/FNR. What does this mean?
- RQ3 results are not easy to analyze... the text states some columns in table 8 that are not there (column "Avg Proj." that is shown at Table 7 and "Rand" that is shown nowhere).
- Authors state that DepImpact and NoDoze have similar runtime performance when clearly DepImpact takes twice as much time.
- DepImpact relies on third-party monitoring system tools.


### Points of interest

- System characteristics, assumptions
  - Dependency weights are calculated with LDA and are based on:
    - timing
    - data flow amount
    - node degree

- Evaluation data sets
  - [DARPA TC Dataset](https://drive.google.com/drive/folders/1okt4AYElyBohW4XiOBqmsvjwXsnUjLVf)



### Questions for discussion

1. How easy can an attacker fool DepImpact? If an attacker can grant access to a host, can he/she manipulate the monitoring tool logs/events to hide its presence/attack? Can the attacker generate bogus events so that the dependency graph is bigger compared to the original attack, thus leading to a more complex analysis?

2. Authors state that DepImpact cannot be executed in real-time due to its cost. Is an attack evaluation still relevant after several days have passed since the security breach? Log rotations and system power-down and power-up can affect the logs/events that are used as input to DepImpact?



## Comparison

_Is this work relevant for your work?_ No. My thesis focuses on attacking ML-based network solutions. In such scenario the packets or flows are used as input to the classifier so there is no built graph dependency that can be used to detect an attack.
