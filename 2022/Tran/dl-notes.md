# Paper Notes
Title: A Stealthier Partitioning Attack against Bitcoin Peer-to-Peer Network

Authors: Muoi Tran, National University of Singapore; Inho Choi, National University of Singapore; Gi Jun Moon, Korea University; Anh V. Vu, Japan Advanced Institute of Science and Technology; Min Suk Kang, National University of Singapore

Reviewer: DL

[Link of the paper]( https://ieeexplore.ieee.org/ielx7/9144328/9152199/09152616.pdf)


## Contribution
Previous work has shown that the most popular blockchains are not decentralized in terms of mining power, which is one of the pillars of blockchain's resilience against attacks. Malicious Autonomous systems (ASes) are capable of performing partitioning attacks on the Bitcoin network. They benefit from plentiful resources and privileged access to the Internet routing infrastructure, making sophisticated network attacks easier to deploy.

The authors aim to demonstrate that Bitcoin is still vulnerable to partitioning attacks from powerful attackers such as big autonomous systems, despite the previously-mentioned fixes to assess these problems. They propose countermeasures to make Bitcoin more resilient against partitioning attacks to solve this.



## Strengths
* Good assessment of countermeasures, splitting them into relevant subcategories (not changing and changing Bitcoin's protocol)

* Discussion on the applicability of existing countermeasures (SABRE) to mitigate the described attacks and why it is not enough.

* Even though it is not highlighted in the paper, the authors maintained close communication with Bitcoin's team to help mitigate this attack.



## Weaknesses
* Despite numerous relevant references to related work, this paper is not self-contained, and it is hard to follow for readers that are not experts in this topic. Most of the references lack explanation. It feels like the readers needed to investigate on their own or read referenced papers to understand this work. This is more noticeable, for instance, for the BGP protocol, double-spending attacks, adaptive attack strategy, and fixes to the Eclipse attack.

* The discussion on this attack's observability is scattered and inconclusive. It would have been relevant to study the observability of flooding nodes with added messages and whether they reveal abnormal behavior compared to regular network behavior.

* The experimental setup is not described in detail and is not reproducible (Section V). The authors do not explain how they simulated them to reproduce a real Bitcoin network and how the results could differ in a real scenario. They could have made a section discussing the possible implications of applying this attack in a real-world Bitcoin network. It would also be very relevant to know how the authors simulated particular ASes and Bitcoin's dimension.

* In Figure 3 (a), it is hard to distinguish the lines, and the plots in Figures 3 and 5 are hard to understand and relate to the experiments described.

* No discussion of practical implications of this attack (even for partitioning attacks in general, the implications are only discussed at a very high level in Section II).


## Points of interest
* Figure 4 shows the largest Tier-2 ASes for the five continents.

* Figure 11 in Appendix A shows the number of BGP hijacking messages in 4 months, presenting seven highly suspicious incidents.

* Appendix D specifies how the Bitcoin emulator performs operations.


## See also
* [Presentation video]( https://www.youtube.com/watch?v=MYuj7iksxKA&ab_channel=IEEESymposiumonSecurityandPrivacy)

*[ What is BGP? | BGP routing explained]( https://www.cloudflare.com/learning/security/glossary/what-is-bgp/)

*[ A Stealthier Partitioning Attack against Bitcoin Peer-to-Peer Network (status on Erebus countermeasures applied to the Bitcoin)](https://erebus-attack.comp.nus.edu.sg/)

* [Countermeasures Against Erebus Attacks]( https://erebus-attack-countermeasures.github.io/)


## Comparison
My work entails studying potential attacks on worldwide relay networks like Tor, mainly encompassing DoS attacks. So, it is interesting to explore similar attacks on networks that share similar characteristics, such as Bitcoin, and think about the traversability of the attacks in both networks and how their differentiating characteristics can complement each other in protection against these attacks. Another exciting aspect is the relevance of the node's distribution and blind trust on which these networks depend, how they can influence their attack surface, and possible countermeasures.


## Questions
1. Why is this attack hard to detect, and are there any ways to detect that this attack is happening?

2. Since this paper is from 2020, did you see if Bitcoin applied any countermeasures? Do you think the possible ethical implications of disclosing this attack were properly handled?

3. Why do the authors consider using Tor or other decentralized relay networks as centralizing or a possible single point of failure for the Bitcoin network?

4. Why is it that botnet operators can no longer carry out this attack?

5. What would be the practical implications of these attacks?
