# Comments on paper-5

Title: A Stealthier Partitioning Attack against Bitcoin Peer-to-Peer Network

Authors: Muoi Tran,  Inho Choi,  Gi Jun Moon, Anh V. Vu, Min Suk Kang

Reviewer: FR

[Link to publication page](https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=9152616)

## Contribution

Highly dependable peer-to-peer networks are at the core of blockchain technology. These networks have been targets for specific attacks such as the Bitcoin hijacking due to the monetary interests involved. This attack seeks to partition Bitcoin’s peer-to-peer network through a well-known BGP prefix vulnerability. While effective, such an exploit requires the perpetrator to expose its identity, deeming it undesirable for reputable ASes.

In this paper, the authors introduce EREBUS, a new attack that allows a network adversary to partition a peer-to-peer network by targeting the connections of one or more Bitcoin nodes. This novel exploit allows for similar results to previous attacks without leaving evidence at the control plane level.

Moreover, this attack does not leverage a bug in the Bitcoin core; instead, it takes advantage of being a network adversary with a large pool of resources (e.g., state level). The exploit is conducted through a man-in-the-middle attack where the offender can control millions of valid IP addresses over an extended period.

Experimental evaluation reveals that Tier 1 Ases are capable of pulling off this attack with limited resource usage over a 6-week period. Worth noting that this attack is particularly important against high-value nodes such as gateways of popular mining pools. Naive solutions such as route measurements or whitelisting were deemed ineffective by the authors. Third-party proxies eventually provide a solution; however, such a solution would potentially break decentralization properties. Working solutions are suggested, such as allowing more outgoing connections for each blockchain node, and have been implemented into blockchain core in recent patches as a direct contribution to this work.


### Strengths

- Due to the attack not exploiting protocol vulnerabilities, figuring out an effective solution is not as trivial as other blockchain exploits. Even though solutions have been applied in recent patches, future patches might include extra fixes to mitigate this attack, proving its effectiveness in the real world;
- The implementation of the Bitcoin node emulator to allow for a certain degree of reproducibility of the experiments and its use of real Bitcoin addr messages provide a strong contribution and credibility to the results presented. 
- 
### Weaknesses

- The attack relies on having the network resources of a Tier-1 AS or a large Tier-2. However, the amount of Tier-1 ASes is limited, and their credibility is a concern. The authors consider the attack to be “virtually undetectable” there is still a chance for detection whilst the perpetrators will likely be concerned with their actions, especially political setbacks. See Q1.
- While the authors claim specific trivial fixes would not be effective, there is no evaluation data to prove that for most of the presented solutions. It would be interesting to see a quick study proving each of those patches ineffective. 

### Points of interest

An interesting countermeasure mentioned by the authors introduces the idea of a peer selection algorithm aware of AS-level topology. The idea of this solution is to leverage the AS numbers to split the IP addresses into two tables rather than using the prefix groups. This mitigates the capabilities of adversaries with IPs distributed across different prefix groups. As a result, only ASes that have control over at least 100 shadow ASes would be capable of pulling off the attack and thus furthering the weakness mentioned above.

An interesting study would be to evaluate the effectiveness of the exploit introduced whilst having further protections against IP spoofing in place. The man-in-the-middle attack leverages the spoofing of shadow IP addresses. However, in a scenario in which further countermeasures against spoofing are in place, the results could differ. See Q2.


### Questions for discussion

1. The limited amount of attackers capable of having the necessary resources are rather limited. Is this a limitation given the number of “suspects” would be rather small, and the bad publicity would be very damaging for any possible attacker?
2. Spoofing the shadow IP communications seems to be a necessary step to pull off this attack, could address IP spoofing rather than this particular exploit lead to an effective mitigation strategy?

## See also

- [Link to related publication](https://btc-hijack.ethz.ch/#:~:text=Partition%20attack%3A%20Any%20ISP%20can,damage%20to%20Bitcoin%20is%20worrying.)

## Comparison

One of the introduced solutions involves SABRE. This system place protects relay to relay connections by forming a densely connected graph of direct peering links. The placement of nodes in a strategic fashion could be related to my work on data partitioning. The idea behind building graphs in which edges and vertex weights can represent different values relevant to the context is at the core of my current research.
