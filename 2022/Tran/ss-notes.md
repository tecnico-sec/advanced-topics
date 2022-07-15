# Comments on _Paper 5 notes_

Title:    A Stealthier Partitioning Attack against Bitcoin Peer-to-Peer Network


Authors:  _ Muoi Tran, Inho Choi, Gi Jun Moon, Anh V. Vu, Min Suk Kang _

Reviewer: _reviewer initials_

[Link to publication page](https://ieeexplore.ieee.org/document/9152616)

## Contribution

_The authors then proposed the Erebus attack, which aims at partitioning the Bitcoin network. The high-level idea is that a capable attacker who controls a lot of IP address space can make an industrial-scale man-in-the-middle attack by operating millions of virtual Bitcoin nodes at "shadow IPs", namely IP addresses where the victim-to-IP-address routes pass through the adversary's network. When the attack is executed, the adversary patiently evicts legitimate IPs in the Bitcoin victim node's internal IP table in favor of the impersonated shadow IPs, followed by adaptively triggering the node to restart after seizing control of enough peering connections. Eventually, the victim node can be completely isolated from the rest of the network while unaware of the attack._

### Strengths

_since this attack does not exploit any particular vulnerabilities of the Bitcoin core; it is still hard to eliminate Erebus completely. The Erebus attack can potentially have similar attack effectiveness against many other cryptocurrencies with a similar network design and implementation to Bitcoin. The adversary ISPs can quietly wait for several weeks while gradually hitting the targeted Bitcoin nodes until the target is finally entirely isolated from the rest of the Bitcoin network because the Erebus attack can be almost unnoticeable.
Since the EREBUS attack exploits no design or implementation bugs of Bitcoin core but only the enormous network address resources of network adversaries, the prevention of the attack (e.g., via fixing bugs) is hard._
_

### Weaknesses

_this test was done in emulation, not in the real world. Therefore it can be a different result when making this attack in a real bitcoin network.
It will take a long time to carry out this attack ultimately._ 

### Points of interest

- _this attack can be executed with a trivial traffic rate._
- _the paper shows us that blockchain systems may be insecure against powerful AS-level adversaries._

### Questions for discussion

1. Exist any defenses against an Erebus attack? 
2. Has the Arbus attack ever been carried out in the real world?
3. It takes several weeks to carry out this attack; isn't it too much for one attack?

## See also

- [link to related publication](https://www.usenix.org/system/files/conference/usenixsecurity15/sec15-paper-heilman.pdf)
-[link to related publication](https://www.semanticscholar.org/paper/On-the-Routing-Aware-Peering-against-Attacks-in-Tran-Shenoi/db7f8535fe9dba9ff23b19ca0d574cf54dee9fe5)

## Comparison

_Studying this research, I found that some attacks may not be detectable, work slowly, and do not even seek vulnerability, so they can easily damage the network.
Reading this article, I found that even blockchain networks that are used to secure other networks can be compromised by an attack. Therefore, my opinion about using blockchain has changed, and I have to consider more carefully if I intend to use blockchain in IoT._
