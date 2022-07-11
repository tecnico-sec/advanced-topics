# Comments on P5

Title: A Stealthier Partitioning Attack against Bitcoin Peer-to-Peer Network

Authors: Muoi Tran, Inho Choi, Gi Jun Moon, Anh V. Vu, Min Suk Kang

Reviewer: RS

[Link to publication page](https://ieeexplore.ieee.org/document/9152616)

## Contribution

Partitioning attacks on the Bitcoin network weakens both availability and consistency of the network, allowing more devastating attacks such as double-spending or 51% attacks. Previous iterations of these attacks were easily detectable due to the nature of the exploited vulnerability.

The main contribution of this work is a new stealthier partitioning attack on the Bitcoin network, undetectable by both control-plane and data-plane detectors and is not easily fixed without significantly changing the Bitcoin core.

### Strengths

* Strong and convincing simulations for proof-of-concept, including detailed simulations of real-world network scenarios and mathematical estimates.

* Provides multiple viewpoints of possible countermeasures and a strong backbone for future work and ponderation into _preventing_ the attack.

### Weaknesses

* The filling of the _new_ tables evaluation (Figure 5) does not consider a real-world scenario where a Bitcoin client already has a full table, which should logically be the common case. 

* A relation between node age and number of entries in its database is missing. This information is crucial to better understand the impact of the simulated attack. 

* While the attack is proven to be possible, its real-world application seems lacking, as it sounds unlikely that any of the big enough AS's to implement this attack would be interested to do so. 

* Only tested in simulated scenarios. A real-world scenario would prove to be more challenging and take into account more network and node changes.

### Points of interest

- The simulation and study done on the geographical distribution of shadow ASes (Figure 4) show very interesting distributions. Specifically, while the paper indirectly mentions China as a possible "nation-state attacker", the Asia-Pacific AS (4.d) does not have nearly as much shadow ASes nor geographical distribution as North America (4.a) and Europe (4.c), so its effectiveness could be questionable.

### Questions for discussion

1. How would you expect a real-world Bitcoin node with an already full table would compare against the simulated data obtained in Figura 5?
2. Why do so many nodes get labeled _terrible_? Wouldn't nodes refresh their connections?
3. What kind of work do the shadow nodes (or the malicious AS impersonating them) need to do in order to _pretend_ to be legitimate? Does it only require pings? Wouldn't the lack of real work (i.e. new updates/blocks) be a source for concern/detectability? 

## See also

- [Hijacking Bitcoin: Routing attacks on cryptocurrencies](https://ieeexplore.ieee.org/document/7958588)
- [Eclipse Attacks on Bitcoin’s Peer-to-Peer Network](https://www.usenix.org/system/files/conference/usenixsecurity15/sec15-paper-heilman.pdf)

## Comparison

While this work has not much in common with my own, the idea of these large-scale man-in-the-middle attacks by ASs can become a real threat to not only Bitcoin and blockchains, but all kinds of systems.

For example, introducing network partitions in geo-replicated, strongly consistent systems that rely on consensus protocols for coordination can easily compromise the systems availability and performance, as defined in the CAP theorem.