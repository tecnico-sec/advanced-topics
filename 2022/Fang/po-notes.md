# Comments on _paper-6_

Title: _Back-Propagating System Dependency Impact for Attack Investigation_

Authors: _Pengcheng Fang, Peng Gao, Changlin Liu, Erman Ayday, Kangkook Jee, Ting Wang, Yanfang (Fanny) Ye, Zhuotao Liu and Xusheng Xiao_

Reviewer: _PO_

[Link to publication page](https://www.usenix.org/conference/usenixsecurity22/presentation/fang)

## Contribution

_What are the significant issues addressed in this publication?_

- When a cyber-attack occurs, experts rely on system monitoring tools to analyze the activities that led to a security breach. Causality analysis is performed over the collected logs in order to identify the attack entry point and its ramifications (e.g., other systems that got compromised). This causality analysis is performed over a system dependency graph where nodes represent system entities and edges represent system events. These graphs are massive, and experts rely on solutions that can reduce their size in order to be able to pinpoint what caused an attack more easily. Current solutions have some downsides: they rely on heuristics that can cause loss of information; or rely on execution profiles to detect anomaly events, which may have to be unfeasible for enterprises with a huge amount of systems dedicated to different tasks. Besides that, graphs should be as small as possible in order to facilitate the analysis, something that current solutions also fail.


_What are the main contributions? (as stated by the authors)_

- Authors propose DepImpact, a tool that facilitates attack analysis by being able to identify critical edges and attack entries in large dependency graphs
- DepImpact can reduce dramatically a dependency graph while still preserving the information that led an attack to happen (critical path)
- DepImpact offers better performance compared to the current state of the art

### Strengths

_In your opinion, what are the strengths of the publication?_

- Clear background on why system monitoring tools are essential and their relation to causality analysis
- Shortcomings of previous work is addressed: PrioTracker and NoDoze they achieve poor performance and provide more extensive graphs compared to DepImpact
- DepImpact was implemented and evaluated against known attacks/exploits (7 attacks from prior work's evaluation and a public dataset released by the DARPA TC program)
- Evaluation clearly states the advantages of DepImpact compared to the current state of the art: up to 72 times more effective in graph reduction without loss of information; ~70% improvement in ranking attack entries
- DepImpact does not rely on third-party services that flag malicious files or IP addresses


### Weaknesses

_In your opinion, what are the weak points in this publication?_

- In the evaluation, the authors study the relationship between several entry nodes and FPR/FNR. The authors state that DepImpact should "stop choosing more entry nodes when including more entry nodes for forwarding analysis will result in a significant increase of the critical component" to have the best FPR/FNR. What does this mean?
- RQ3 results are not easy to analyze... the text states some columns in table 8 that are not there (column "Avg Proj." that is shown in Table 7 and "Rand" that is shown nowhere).
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

1. How easy can an attacker fool DepImpact? Suppose an attacker can grant access to a host. Can he/she manipulate the monitoring tool logs/events to hide its presence/attack? Can the attacker generate bogus events so that the dependency graph is more extensive than the original attack, thus leading to more complex analysis?

2. Authors state that DepImpact cannot be executed in real-time due to its cost. Is an attack evaluation still relevant after several days have passed since the security breach? Log rotations and system power-down and power-up can affect the logs/events that are used as input to DepImpact?


## Comparison

_Is this work relevant to your work?_ No. My thesis focuses on attacking ML-based network solutions. In such a scenario, the packets or flows are used as input to the classifier, so no built graph dependency can be used to detect an attack.
