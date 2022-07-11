# Comments on paper-1

Title: VerLoc: Verifiable Localization in Decentralized Systems

Authors: Katharina Kohls, Claudia Diaz

Reviewer: FR

[Link to publication page](https://www.usenix.org/system/files/sec22summer_kohls.pdf)

## Summary

Previous works used timing probes to targets from trusted landmarks that have a known location which allow for street level granularity locations but rely on a trusted setup.

This setup is vulnerable to attacks that seek to manipulate timing measurements or even malicious landmarks that lie about their location. Hence, this approach is not adequate for a decentralized setting.

Motivation for this work:
- Overlay anonymous communication networks - where to place relays.
- P2P networks that maintain a blockchain - location diversification of nodes.

Contributions:
- Verloc introduces a timing based verification algorithm that is able to verify geolocation in a fully decentralized network in which up to 20% of the nodes can be malicious.
- This work also proposes securely scheduled pairwise Round Trip Time (RTT) measurements to thwart attacker manipulations whilst applying trillateration to estimate the whereabouts of each node.
- They use a broadcast channel to verify all the geolocations. It is worth noting that the measurements comprise an overhead of a few thousand pings which remains constant as the network grows.
- Lastly, the evaluation performed shows that VerLoc performs better in the wild than in a controlled environment. To deal with scenarios in which there are adversarial nodes they introduce a confidence score to qualify true and false reported locations.

### Strengths

- Tackles node location problem in a decentralized setup whereas previous systems were vulnerable, for instance, to malicious landmarks.
- Robust to various attacks through different security mechanisms. Random beacons as a seed for schedule measurements stop attackers from controlling this interval. The nonce present in the ICMP echo message allows for message freshness. Can also be hashed with a shared secret to also prevent man-in-the-middle attacks.
- Very strong evaluation section comprising both a simulated scenario and real scenario. Detailed study of each attack possibility and possible solutions.

### Weaknesses

- Where for most systems a median error of 60km would be acceptable, there are systems for which it won’t be. For example, the location of mobile high value nodes. Furthermore, a 60km range can easily output a different country/jurisdiction zone which is an important result of this kind of system.
- It is not trivial to figure out when to update the pre-computed internet model that is used, how long can it be valid for and is the system capable of detecting when to update it.


### Points of interest
- It is assumued that can attacker is unable to censor a node’s read or write access to the group channel.
-- Secure broadcast channel with byzantine fault tolerance is a system requirement as well. See Q1 below.
- Another assumption mentions that all participants should be able to authenticate a group channel without being tricked by adversaries

### Questions for discussion

1. Given the system requirements, would it be feasible for an attacker to stop a legitiamte node from entering an epoch by dropping its messages to the group channel?
2. In line with the previous question, in a publicly accessible network, only tolerating up to 20% malicious nodes seems rather dangerous given they can easily join and take control over the network?

## Comparison

This publication is completely out of scope of my research work as I focus on distributed systems and data partitioning.