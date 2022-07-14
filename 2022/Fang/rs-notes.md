# Comments on P6

Title: *Back-Propagating System Dependency Impact for Attack Investigation*

Authors: *Pengcheng Fang, Peng Gao, Changlin Liu, Erman Ayday, Kangkook Jee, Ting Wang, Yanfang (Fanny) Ye, Zhuotao Liu, Xusheng Xiao*

Reviewer: RS

[Link to publication page](https://www.usenix.org/system/files/sec22summer_fang.pdf)

## Contribution

*Causality analysis* has become a widely used technique for analyzing and identifying both intrusion points (*POI*) and attack ramifications. However, current techniques create dependency graphs of hundreds of thousands of edges, quickly degrading its usefulness for security analysis purposes.

The authors introduce ***DepImpact***, a framework to identify critical edges and attack entries in large dependency graphs by combining novel techniques for identifying critical edges, ranking nodes w.r.t its impact to the POI, and creating a significantly reduced causal graph for better security analysis.

### Strengths

- Remarkable reduction of graph size (4500x reduction) without losing accuracy (no critical edge missed).
- Wide list of common attacks used in the evaluation, including more challenging multi-host intrusion attacks.

### Weaknesses

- A significant amount of prior knowledge is required to understand the edge dependency weight computation truly, and little intuition is given to non-specialized readers.
- The exclusion of phishing attacks leaves much to be desired, as it is one of the most common attack vectors.
- Some erroneous formulas and explanations are given in the "Evaluation Metrics."
- While the authors suggest prevention mechanisms for attacks that abuse DepImpact mechanisms, none seem realistic and should have been explored in the evaluation. Moreover, mitigation such as considering multiple POI is unrealistic when it is not the system that defines the POIs.
- No long-term attacks and scenarios were tested in the evaluation. While arguments such as "cheap storage" are used, when considering large-scale deployments with hundreds or thousands of machines over long periods, performance and scalability can be significantly affected, with cost becoming a real concern.

### Points of interest

- The chosen attacks seem relevant, especially the inclusion of multi-host attacks. Some more information on how multi-host attack graphs are merged would be interesting.

### Questions for discussion

1. With prior knowledge of the feature extraction formulas, couldn’t an attacker manipulate its attack to disrupt the algorithm by adding multiple fake/useless edges?
2. How would the algorithm scale w.r.t the number of logs and data? The authors mention cases where logs can be kept “during years.” However, none of the experiments seem to include longer-duration scenarios. Experimental data also does not include information and comparing execution time and used memory between different attacks.
3. The authors suggest stopping choosing more entry nodes in the analysis if it “significantly increases the critical component.” How would this significance and increase be defined? Cases like the “Shellshock” attack in Figure 5 require six nodes to avoid false negatives. However, with only 2 nodes, we see an increase of 10% of False Positives in Figure 6, directly correlating to the increase of the critical component and possibly stopping the addition of new entry nodes.

## See also

- [NoDoze: Combatting Threat Alert Fatigue with Automated Provenance Triage](https://www.ndss-symposium.org/wp-content/uploads/2019/02/ndss2019_03B-1-3_UlHassan_paper.pdf)

## Comparison

As some of my work involves providing causal consistency to transactions, large causal dependency graphs are a well-known problem to me, especially in works that depend on *explicit dependencies* as is the case of DepImpact. Future work should look at techniques to mitigate the amount of causal information without losing critical data, as done in previous explicit dependencies causal works.
