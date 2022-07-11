# Comments on _paper-1_

Title: _VerLoc: Verifiable Localization in Decentralized Systems_

Authors: _Katharina Kohls, Claudia Diaz_

Reviewer: _MF_

[Link to publication page](https://www.usenix.org/conference/usenixsecurity22/presentation/kohls)

## Contribution

This paper addresses the challenge of verifying the geolocation claimed by nodes in a fully decentralized network, in a reliable and robust way, without relying on trusted authorities. 
The authors propose VerLoc, which uses a novel algorithm based on the measurement of round trip times between network nodes, robust to adversarial manipulation.
To allow the conversion of measured times into geographical distances, the authors conduct an empirical study to produce a network propagation model, robust to network noise.
The authors also evaluate VerLoc in simulation settings, to study how different parameters can affect VerLoc’s accuracy, and in the wild, using a prototype integrated into the Nym network, to evaluate VerLoc’s performance in the presence of active adversaries.


### Strengths

This paper presents a novel approach to reliably verifying node locations with a confidence score. A strong point of this work is that VerLoc is fully decentralized and does not require the intervention of trusted entities or landmarks with a known location. 
Another strong point of this work is how the authors overcome the difficult challenge of network noise and variance in transmission speed, crucial to their protocol, by conducting an empirical study and deriving a propagation model to be used by VerLoc nodes to compute the verification algorithm.
The authors deployed a prototype version of VerLoc in the Nym network and performed experiments in the wild, allowing a performance evaluation in the real world, which is very valuable.


### Weaknesses

I believe the authors assume a lot of knowledge about secure broadcast with Byzantine fault tolerance work and fail to explain key concepts that would help the reader to understand its implications in a system, such as the availability guarantees and timing assumptions (e.g. what is the minimum epoch length?). Furthermore, they do not use this for the evaluation and state that this choice makes the system more susceptible to adversarial attacks, but do not explain which.
On the same note, the authors assume that there are no failures in the network, which to me is not a realistic assumption, especially in the presence of active adversaries. 
Concerning the evaluation, the authors only evaluate the number of references in the performance of VerLoc for a specific number of network nodes (1000), which is the number of nodes they use in the experiments. But I wonder how this number behaves in other network settings. 
The authors also state that the simulations represent a difficult deployment scenario and the experiments in the wild performed better because of it. However, in the results section, the authors indicate that they selected nodes in Europe to be able to compare them with the simulation results - I did not understand what these difficult settings were and what were their direct implications. 
Lastly, in Section 5.5, concerning VerLoc’s breaking point, the experiments seem to only consider a static number of references, could this be tackled with a greater R?


### Points of interest

The deployment in a real-world scenario (Nym network) and the generated propagation model. 


### Questions for discussion

1. What would happen if a node delays its responses indefinitely?
2. Is the ideal R (reference number) independent of the number of total network nodes?
3. Why are the simulation settings considered to be a difficult deployment scenario?


## Comparison

The topic of this paper is very different from my work, but it helped me understand how to structure sound and complete papers, backed up by both empirical and experimental studies.