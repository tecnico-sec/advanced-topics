# Comments on _paper-0_

Title: _On the (In)Security of 1090ES and UAT978 Mobile Cockpit Information Systems–An Attacker Perspective on the Availability of ADS-B Safety- and Mission-Critical Systems_

Authors: _Syed Khandker, Hannu Turtiainen, Andrei Costin, Timo Hämäläinen_

Reviewer: _MF_

[Link to publication page](https://ieeexplore.ieee.org/document/9749067)

## Contribution

This paper addresses the vulnerability to DoS attacks by mobile cockpit information systems. The authors present a security study of commercial MCIS, with 68 test configurations, implement and reproduce ADS-B DoS attacks over UAT978 (the first-ever) and 1090ES and demonstrate that most implementations are vulnerable to DoS attacks.


### Strengths

This paper addresses a pertinent problem since air-traffic control systems are considered critical applications which require great availability. The continuous increase of aircraft in the airspace demands more accurate and efficient systems.
The authors provide a great explanation of the problem's relevance, the currently proposed solutions to mitigate the problem, and the limitations of current studies.
Overall, the paper is well structured and easy to read for non-experts in aircraft systems. 

### Weaknesses

Concerning the experimental setup, I did not understand how the attack payload transmission was performed, namely, if it was only one SDR sending messages. If so, I believe this is unrealistic and a step back compared to related studies. Moreover, the authors never state the rate of the requests, only that they are sent "very quickly," which is a bit vague.
It would also help to have an example of an attack payload.
Concerning the results, I found it confusing to explain some of the results prior to showing them.
Additionally, I think it would help the reader to have the figures available on the same page they are referenced. The authors also never describe the IQ abbreviation.

### Points of interest

The hardware and software combinations used in the experimental setup can be helpful for other researchers to perform related studies.

### Questions for discussion

1. Would any of the proposed solutions help mitigate the denial of service attacks?
2. Would the paper improve if the transmission was performed N-1?

## Comparison

The topic of this paper is very different from my work. However, there are some similarities and lessons to learn. I am tempted to perform a large-scale analysis related to GDPR violations in the wild, so this paper helped me understand how to structure the paper and which aspects are relevant to an experimental study.
