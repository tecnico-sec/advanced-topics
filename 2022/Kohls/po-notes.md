# Comments on _paper-1_

Title: _VerLoc: Verifiable Localization in Decentralized Systems_

Authors: _Katharina Kohls, Claudia Diaz_

Reviewer: _PO_

[Link to publication page](https://www.usenix.org/system/files/sec22summer_kohls.pdf)

## Contribution

_What are the major issues addressed in this publication?_

- Services may benefit from location information (e.g., clients' communication with dispersed servers in order to assure higher security and resiliency). The main issue is that servers from such services may not provide location information. Geolocation IP databases may also have outdated information.


_What are the main contributions? (as stated by the authors)_

- Authors propose a solution named VerLoc, capable of determining the geolocation of nodes in decentralized networks. Such a solution can determine location even in the presence of attackers and without requiring the trust of location landmarks (these landmarks may have incorrect location definitions).


### Strengths

_In your opinion, what are the strengths of the publication?_

- Prototype deployed on a real network (Nym)
- VerLoc is fully decentralized, meaning that it works on its own, not requiring a centralized infrastructure
- VerLoc relies on ICMP, a well-known protocol, to obtain RTT information. By including additional information on variable length fields of this protocol, it is possible to prevent replay attacks and guarantee integrity and authentication (include a nonce that can be hashed using an established shared secret)
- Good theoretical definition of how to define the distance between nodes
- Confidence score is used to accept or reject location from nodes and, in this way, filter attackers providing misleading location information
- Thorough evaluation
- Good security analysis


### Weaknesses

_In your opinion, what are the weak points in this publication?_

- Solution requires nodes to provide location information ("ideally with an error of fewer than 10km"). No information on how the node obtains such information. GPS? Are they inputted by the user?
- Trying to obtain location based on RTT is not very reliable: nodes on the internet are not connected in a straight line, meaning that their RTT will be higher due to the zig-zag connection between ISPs. Multiple internet access connections are possible today (fiber, copper, radio, satellite), making the connectivity/RTT between nodes to be different depending on the medium. Congestion and traffic asymmetry also takes a big effect on the measurements. These aspects show up on the evaluation: an average location error of 122km in simulation and 178km in practical evaluation.
- Attackers can affect the reliability of protocol by controlling a small subset of the nodes (>20%).
- Evaluation focused on a single continent: Europe. The presented results may be "best case scenarios" because Europe ISPs are well interconnected. Communication between different continents and intra-continent (e.g., South America) may be worse than the presented results because ISPs in such regions are not well interconnected/peered. In such cases, we may observe an increase of "false rejections" of location information.

### Points of interest

- System characteristics, assumptions
    - Fully decentralized
    - It is assumed that two nodes can perform pings between each other. While not commenting on the paper, this assumes that both have public IPs and ICMP traffic is not being filtered by Firewalls in the middle of the network
    - Considers that the upper bound transmission speed on the internet is 0.67c

### Questions for discussion

1. VerLoc has a huge location error due to the nature of RTT measurements on the internet. Suppose applications/users accept obtaining location information not very precisely. Why not simply discover the ISP owner of the IP of a node based on the IP prefix? Such information is publicly available (by looking to BGP route tables and/or by querying IANA). An ISP is bound to a country (or a group of countries) which is a good way to discover more or less the location of a node.
2. Is the additional overhead required by VerLoc acceptable considering its somehow limited accuracy in order for services that rely on it to provide better performance and security to its users?
3. How secure can VerLoc be if it is considered robust with up to 20% nodes in control by the attacker? In the Nym evaluation, this represented ~700 nodes. An attacker can have a botnet and add such malicious nodes to the decentralized network in order to disrupt this location service.


## Comparison

_Is this work relevant for your work?_ No
