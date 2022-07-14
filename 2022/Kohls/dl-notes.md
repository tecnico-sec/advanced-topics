# Paper Notes
* **Title:** VerLoc: Verifiable Localization in Decentralized Systems

* **Authors:** Katharina Kohls and Claudia Diaz

* **Reviewer:** DL

* [Link to publication page](https://www.usenix.org/system/files/sec22summer_kohls.pdf)


## Contribution

* Major issues: Lots of systems rely on knowing the correct locations of their users for various purposes. However, users have the possibility to lie, putting at risk the efficacy of the systems' purposes, such as protecting users' privacy or providing resilience. VerLoc provides a way to verify which users are lying about their location without requiring additional entities.

* As stated by the authors: Build a system that verifies the claimed geo-locations of network nodes, supporting up to 20% malicious nodes, in a fully decentralized manner. For this, the authors used distributed timing probes to determine the distance of a node to multiple other nodes and trilateration to verify if the distances retrieved add up to infer a location or if they don't make sense; thus we can affirm with a level of certainty (confidence score) that the node is malicious and was trying to trick the other nodes about its location, or about another nodes' location by lowering the score of both nodes involved.


## Strengths
* Good coverage of potential network attacks and potentiation of existing cryptographic mechanisms: blockchain for immutable location records, freshness with unpredictable nonce; man-in-the-middle with a hash with a pre-established key.

* Wide reflection on possible attacks and in which situations they can happen in the experimental setup, as well as the additional threats and respective future work to solve them.

* Combination of simple algorithms (triangulation combined with zones simplification) and protocols (multiple ICMP probes) that are scalable introduces little overhead on the network while significantly mitigating the effects of malicious colluding nodes. This is particularly important since anonymity networks already suffer from scalability and latency issues.


## Weaknesses
* They present no mention or studies on the node distribution of Tor and Nym networks, just the natural geographical advantage of some zones. As far as Tor goes, the node distribution is highly skewed, so choosing references randomly accentuates the problem of directional diversity. Malicious nodes can exploit this to choose a strategic location where lying to references is significantly easier due to the network's unbalanced distribution in that area.

* Authors do not discuss particular situations where propagation speed can be significantly lower, such as in censored regions where throttling is applied. Would an honest node behind China's Firewall have its score hindered? 

## Points of interest
* Figure 4 describes the Zone Verification Process.

* Comparison of Figures 9 and 10 showing how increasing malicious nodes affects the reliability of confidence scores. 5.6.1 Benign Framing nodes discusses how malicious nodes can lower the confidence score of honest nodes

* 5.6.3 Adversaries in the underlying network and 5.6.4 Compromised Broadcast Channel comprise some problems that may require when applying VerLoc to existing networks.

## See also
* [Nym vs other systems](https://nymtech.net/docs/stable/overview/nym-other-systems/)
* [Mapping How Tor's Anonymity Network Spread Around the World](https://www.wired.com/2015/09/mapping-tors-anonymity-network-spread-around-world/)


## Comparison
* This work tries to solve a potential weakness in anonymity networks. It may even provoke changes to the communications involved in these networks, producing fingerprints that are interesting to investigate.

# Questions
1. How are censorship mechanisms such as throttling taken into account for the network noise allowed?

2. How does picking random references to help prevent attacks? This could work in an ideal scenario, but due to geographical and socioeconomic factors, the node distribution is highly skewed, making it more likely that the references are not evenly distributed around the target node, countering the accuracy of trilateration at detecting wrongly claimed locations and consequently lowering the scores of honest nodes

3. What kind of problems can arise when combining 
