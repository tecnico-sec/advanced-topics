# Comments on _Paper 1 notes_

Title: VerLoc: Verifiable Localization in Decentralized Systems

Authors: _Katharina Kohls , Claudia Diaz_

Reviewer: _SS_

[Link to publication page](https://www.usenix.org/conference/usenixsecurity22/presentation/kohls)


## Contribution

This study addresses a long-standing problem: accurately detecting the geo-location of nodes in decentralized networks under hostile environments without relying on third parties. According to the author, active attackers that control a portion of nodes publish fake positions and intentionally modify measurements. The authors design, build and evaluate VerLoc. This system permits completely decentralized verification of network node claimed geo-locations to overcome this issue.
When we use the tore network to transfer traffic, there are many servers in different parts of the world, also called tore relays. However, some of these relays are controlled by people who are not reliable and introduce themselves as a reliable relay. However,  we do not know whether this relay is unreliable or not. If a node presents itself in a trusted area, how can we tell if that node is what it claims to be and is correct? 
The Verloc system examines the area declared by a node and confirms or rejects it and whether it could be trusted or not.

### Strengths

- The idea of identifying where the nodes are and whether we can trust them is fascinating.
- One of the strengths of this project is the effort to discover invalid nodes. It also uses the ICMP protocol to obtain packet time, and the protocol packets are small and fast, and it's an easy way to get round trip time to any destination.
- Another strength of this project is the use of blockchain. A blockchain stores all the results in a decentralized system, and everyone can access these results.
How can achieve this goal:

_-Localize nodes_

_-Verify the results_

_-Decentralize the process_


### Weaknesses

- Because this project is implemented as a simulation in real networks, the time obtained by the ICMP protocol depends on different conditions. It can be variable, so finding the exact location of a node can be challenging. In the actual network, there may be a lot of noise, and also the processing speed of the routers and the bandwidth of each are different, so the time obtained can be different, and also the amount of load on each router in response to the ICMP package can be influenced.
- Using the China Blockchain channel intends to decentralize processing and ensure that everyone has access to information in a completely secure way. However, one of the drawbacks of using the China Blockchain is that, over time, the volume and size of the China Blockchain will increase. Other problems occur._ 

### Points of interest

- Prototypes of this system have been tested on the NYM network and the actual network, which has been able to test up to 60 km. Since this experiment was conducted in Europe and the countries are close to each other due to their size, it can be said that it can examine up to 1 country.


### Questions for discussion

1. How would you fix this if something like Cloudflare on the network between the two nodes prevented receiving and responding to the ICMP ping?
2. When you check and confirm a node, you compare the results of the offending nodes and get to a small area if the nodes you use for the test yourself in this test are unreliable and do not show real-time. How can this error be corrected?


## See also

- [On the Challenges of Geographical Avoidance for Tor](http://poepper.net/papers/NDSS19-TrilateraTor.pdf))
- [How to Catch when Proxies Lie: Verifying the Physical Locations of Network Proxies with Active Geolocation](https://dl.acm.org/doi/pdf/10.1145/3278532.3278551?casa_token=craj0wL-3poAAAAA:0NWqmHvYWhwn9EEy4OiNMLbS8vf8Ura5fo6Rg0KvSJ4K4oa0dNR-jwD5r9jzTfyxCjh82VxN6uE9Mw)


## Comparison

- It is an exciting idea, I work in the field of IoT, and I can use this idea to get the position of sensors in the network.

- This project tries to detect unsafe nodes and prevent communication with them. However, in the work that I am doing, I intend to establish a secure connection between the sensors and the cloud with light and secure identification


