# Comments on _paper-6_

Title: _Back-Propagating System Dependency Impact for Attack Investigation_

Authors: _Pengcheng Fang, Peng Gao, Changlin Liu, Erman Ayday, Kangkook Jee, Ting Wang, Yanfang (Fanny) Ye, Zhuotao Liu, Xusheng Xiao_

Reviewer: _MF_

[Link to publication page](https://www.usenix.org/system/files/sec22summer_fang.pdf)


## Contribution

This paper focuses on improving causality analysis on system auditing data to investigate the source of attacks. The authors propose DepImpact, a framework that relies on the use of dependency weight computation for both back propagation and forward causality analysis to identify critical edges and attack entries in dependency graphs. They evaluate the size of the resulting dependency graphs and show that DepImpact reduces its size by 4611x when compared with other state-of-the-art techniques.

### Strengths

This paper investigates a novel approach for causality analysis, which significantly reduces the dependency graph that is used for attack investigation, preserving the critical dependencies.

* A strong point of this work is that, by reducing the resulting dependency graph to the critical edges and nodes, DepImpact greatly improves the effort of inspection, which may widen the adoption of such frameworks and further improves the security of systems.

* Another strong point is the fact that the proposed methodology seems to be suitable and appealing for other research domains, such as static analysis based on graphs.


### Weaknesses

. The authors do not evaluate the coverage of the framework (covered attacks) or justify the choice of the attacks. This is an issue to me because, for example, in the NoDoze paper, the reported edge/node size is significantly lower than what is reported in this paper, with very comparable values (for different attacks). This may be due to the evaluation setup (different environment) but it is not discussed. It also appears to not cover more sophisticated but researched attacks, such as delay attacks (check the first paper in the See Also section), which may reduce DepImpact's accuracy to more recent real-world attacks. 

* Part of the evaluation seems a bit incomplete. The paper does not contain a resource utilization evaluation. This would allow the reader to understand if there is any trade-off involved in this reduction. The authors do not evaluate the applicability of the framework, only state that it works in Ubuntu 18.

* In Phase II, DepImpact first employs state-of-the-art dependency reduction techniques, such as edge merge [78]. However, in the evaluation is not clear what is the reduction resulted from existing dependency reduction techniques and later from DepImpact, which makes it unclear what is the contribution of DepImpact.

* Along the paper, the authors present some relevant values used for the computations. For example, in Section 4.3.1, they state that they set the threshold δ as 1e-13 since it gives robust results, but never justify this value.


### Points of interest

The proposed methodology, more specifically, the forward causality analysis may be extended to investigate other critical consequences related to the attack.


### Questions for discussion

1. Can attackers include "dummy" irrelevant system activities related to the POI to decrease DepImpact's accuracy?
2. What are the gains of this approach when compared with ML systems that monitor outlier behavior?
3. DepImpact filter out failed system calls. Isn't this conservative and may lead to false negatives?

## See also

- [Validating the Integrity of Audit Logs Against Execution Repartitioning Attacks](https://dl.acm.org/doi/abs/10.1145/3460120.3484551)
- [NoDoze: Combatting Threat Alert Fatigue with Automated Provenance Triage](https://www.ndss-symposium.org/ndss-paper/nodoze-combatting-threat-alert-fatigue-with-automated-provenance-triage/)

## Comparison

The proposed methodology - identifying critical information by weighing nodes - may be relevant for my work as I have a static analysis component that includes lots of "garbage" that is being processed and reducing its performance.
