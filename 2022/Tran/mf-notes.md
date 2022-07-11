# Comments on _paper-5_

Title: _A Stealthier Partitioning Attack against Bitcoin Peer-to-Peer Network_

Authors: _Muoi Tran, Inho Choi, Gi Jun Moon, Anh V. Vu, Min Suk Kang_

Reviewer: _MF_

[Link to publication page](https://ieeexplore.ieee.org/document/9152616)


## Contribution

This paper explores a stealthier version of the known prefix hijacking attack without requiring routing manipulations, which allows to partition the Bitcoin network without being detected.
The authors propose the EREBUS attack, which relies on deploying a natural man-in-the-middle network of the peer connections of selected Bitcoin nodes to control their peer decision.
They show that any Tier-1 or large Tier-2 ASes can control a bitcoin node within 5-6 weeks.

### Strengths

This paper investigates a novel approach, which takes topological advantage of being a resourceful network adversary, instead of exploring vulnerabilities in the Bitcoin core.

* A strong point of this work is that it provides a more patient approach to avoid the attack detection, making the attack invisible to control-plane monitors. This also takes significantly more time to take effect and requires a notable evaluation effort.

* Another strong point is the discussion of effective countermeasures to EUREBUS and the possible challenges involved in deploying them. 


### Weaknesses

* The authors assume some prior knowledge of Bitcoin and protocols (e.g. BGP) that would help the reader to have some perspective of the treat model and comprehend the attack implications of EREBUS, for example, if there is any relevant difference between public and private nodes and if it would still be feasible in the latter, or who would benefit from these attacks. On the same note, this also reflects on understanding the reasoning behind some choices, e.g., the evaluation setup in Section IV-B.

* EUREBUS relies on impersonating millions of shadow IP addresses, which intend to replace all the outgoing connections of the victim. However, doesn't the victim expect correct behavior from these connections, and couldn't this be used to detect the attack? (I am no expert in this topic, so I cannot detail this more). The authors do not discuss the impersonation effort and limitations.

* The attack is undetectable by control-plane anomaly detection systems since it does not require route manipulation. Instead, it only uses data-plane messages. The authors state that it may be possible to detect data-plane traces of the attack but do not discuss if data-plane detection systems exist, if they are commonly deployed in such networks, and what limits them to correlate the attack (even if they may not be able to do it yet, but more sophisticated systems may appear).
  
* The attack takes several weeks to complete. The authors do not discuss if there are dynamic conditions of the network that could change in the course of the attack and decrease its success potential.


### Points of interest

The focus on sophisticated and powerful (costly) attacks can motivate interesting and relevant research of equally powerful defenses.

### Questions for discussion

1. Who benefits from these attacks in the real world, and in which context? 
2. How feasible is the attack in the real world? I do not have perception of the cost of an attack like this.
3. This paper is from 2020, are there any newer solutions that help to mitigate these attacks?

## Comparison

This work focuses on a different approach than the ones I was familiar with: it does not focus on attacking the system itself but rather on its foundations/principles, which once again helped me to expand my horizons and I believe will help my research as I search for new ideas.