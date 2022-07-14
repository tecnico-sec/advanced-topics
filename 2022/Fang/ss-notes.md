# Comments on _Paper 6 notes_

Title:     Back-Propagating System Dependency Impact for Attack Investigation


Authors:  _ Pengcheng Fang, Peng Gao, Changlin Liu , Erman Ayday, Kangkook Jee, Ting Wang, Yanfang, Zhuatao Liu, Xusheng Xiao _

Reviewer: _reviewer initials_

[Link to publication page](https://www.usenix.org/conference/usenixsecurity22/presentation/fang)

## Contribution
_Today, most businesses are done online, so cyber attacks have increased and affected businesses, causing significant financial losses. Most of these attacks occur using vulnerabilities in the system. Today, one of the challenges in dealing with cyberattacks is investigating and identifying vulnerabilities. To combat cyber attacks, security experts try to find a security problem by reviewing reports from monitoring systems. However, the sheer volume of this data has made things very difficult. 
Therefore, The authors proposed that the DEPIMPACT, introduced with a new framework, can simplify the investigation by identifying the essential edges of the attack inputs in the dependency diagrams._

### Strengths

_DEPIMPACT dramatically decreases the complexity of revealing attack phases by preserving attack information and having a size substantially smaller than the original dependency graph, enabling attack analysis. 
One of the strengths of this article is the use of more than 100 million system auditing events  for DEPIMPACT testing. Spend a short time presenting data analysis results._
_

### Weaknesses

_To test performance DEPIMPACT,focuses only on one attack model, an attack by an out-of-system attacker that attacks the system remotely.
Kernel-level cyberattacks have not been investigated in this experiment.
This program can not work in real-time, so that it can be used after an attack. Therefore, it can only be used to prevent future attacks.
Other systems must be used to make it possible to use DEPIMPACT, which means that the DEPIMPACT program can not work independently, and the required data must be collected using other programs._ 

### Points of interest

- _Provide analysis reports in less time than other existing systems._
- _DEPIMPACT is extremely good at identifying important edges and attack entries._


### Questions for discussion

1. According to the article, this program does not work in real-time; how can this program be used to deal with cyber-attacks? 
2. Several different attacks may coincide. Can DEPIMPECT detect different attacks from one set of data?

## See also

- [link to related publication](https://www.scinapse.io/papers/2965563623)
-[link to related publication](https://www.scinapse.io/papers/2998038410)



## Comparison

_By reading this article, I concluded that when I want to examine various attacks on the IoT network, I use the ideas in this article to examine the data obtained._






















