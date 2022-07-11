# Comments on P0

Title: On the (In)Security of 1090ES and UAT978 Mobile Cockpit Information Systems—An Attacker Perspective on the Availability of ADS-B Safety- and Mission-Critical Systems

Authors: Syed Khandker, Hannu Turtiainen, Andrei Costin, Timo Hämäläinen

Reviewer: RS

[Link to publication page](https://ieeexplore.ieee.org/document/9749067)

## Contribution

While next-generation air transportation systems have gradually been adapting the usage of Mobile Cockpit Information Systems (MCIS) for surveillance of airborne traffic, the development process of said systems has not adapted their security measures with regards to its criticality and importance in the private and public aviation industry. This paper addresses the resilience and security of the most popular MCIS. 

The main contributions of this work include a security analysis of multiple MCIS, the impact of Denial-of-Service (DoS) on EFBs and a vulnerability demonstration of ADS-B datalink implementations.

### Strengths

* Strong motivation, presents the high risk and impact that these systems malfunction may bring; 
* Includes a detailed and complete survey of related work on ADS-B attack surfaces and how it sets itself appart;
* Indepth analysis of a wide number of MCIS, including the most popular software, hardware and its multiple combinations.

### Weaknesses

* While results demonstrate that systems are affected by the attacks, little analysis is done on __why__ they are affected and which factors most influence these results, specially for the 1090ES case. 
* It is not clear in the result analysis whether some of the DoS issues found, specially regarding message dropping, are software issues, hardware issues or both.
* Its usage in a realistic environment is not mentioned and is somewhat questionable.

### Points of interest

- Detailed exposition and comparision with related work, a good starting point to enter the world of ADS-B security.

- Large data set of the most used hardware and software, along with results correlation with previous related work (fuzzing attacks).

### Questions for discussion

1. What conclusions can we obtain from the 1090ES DoS results? 
2. Are the valid messages dropped an hardware or a software issue? The attack payload seems to overflow the highest maximum capacities of some MCIS (SkyEcho2), but it is not clear if the dropping is due to hardware or the software cannot handle the ammount of addresses. 
3. Arent "valid message dropped" and output clogged the same issue? Does this differentiation mean that UAT978 are able to show all aircrafts, but are not able to provide all updates to them?
4. How was the DoS message content created? We see that fuzzing works on the applications, what if the application crashes are related to content rather than the DoS? 

## See also

- [Deeper analysis on EFB fuzzing](https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=9709804)
- [Broader studies of ADS-B attacks](https://jyx.jyu.fi/bitstream/handle/123456789/79806/Cybersecurity_attacks_on_software_logic_and.pdf?sequence=1&isAllowed=y)
- [Analysis of 1090ES packet loss](https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=6815901)
