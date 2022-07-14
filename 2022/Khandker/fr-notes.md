# Comments on Paper 0

Title: On the (In)Security of 1090ES and UAT978 Mobile Cockpit Information Systems—An Attacker Perspective on the Availability of ADS-B Safety- and Mission-Critical Systems

Authors: SYED KHANDKER , HANNU TURTIAINEN , ANDREI COSTIN , AND TIMO HÄMÄLÄINEN

Reviewer: FR

[Link to publication page](https://ieeexplore.ieee.org/document/9749067)

## Contribution

The study focuses on ADS-B technology's vulnerabilities against radio-linked attacks by transmission capable software-defined radio (SDR). The experimental results show that DoS attacks at the packet level led to system crashes whilst attacks on the reception impacted the transmission capacity of the systems.

The increasing number of aircraft has led to research that seeks to replace radar-based air traffic control (ATC) and air traffic management (ATM) by digital and satellite-based navigation systems. In the US, automatic dependent surveillance-broadcast (ADS-B) was implemented as the solution. The idea of ADS.B is to periodically broadcast information about an aircraft to the ATC and other nearby aircraft via a radio frequency data link. 

It is common to use ADS-B together with mobile cockpit information systems (MCIS) by connecting the ADS-B transceiver to an intelligent device capable of displaying the navigation data through an electronic flight bag (EFB) application. The most critical component of ADS-B is the positional information, computed via the global navigation satellite system (GNSS).

ADS-B technology does not use authentication or encryption, leaving it vulnerable to attacks and, by doing so, leaving the MCIS vulnerable as well. Mobile devices have computational, power, and memory constraints that also amplify the success chance of an attack.

The focus of the paper is on MCIS vulnerabilities rather than ADS-B, however, the latter is a critical component of the former. As such, the main contributions of this paper, as stated by the authors, are: 

- A systematic and comprehensive study of the (in)security of commercial MCISs.
- Impact of the attacks on a number of EFB applications.
- Implementation of a first-ever ADS-B attack over UAT978.
- Demonstration that both UAT978 and 1090ES are comparably vulnerable to generic and available cyberattacks.

### Strengths

- The publication focuses on a topic that there is not a lot of relevant prior research on. Whilst ADS-B vulnerabilities have been investigated in the past, MCIS has not been investigated to the same degree. 
- Experimental evaluation is conducted on various configurations, allowing for a clear view of how each system can behave differently to a DoS attack whilst providing the reader with an idea of how many alternatives there are for MCIS systems.
- Suggestion and creation of a framework capable of evaluating DoS and Fuzzing attacks on MCIS systems capable of measuring the effects of said attacks on state-of-the-art commercial level MCIS systems

### Weaknesses

- Whilst the paper tries to emphasize its focus is on MCIS systems, a considerable portion of the attacks seem to be carried out through the ADS-B receivers (which are indeed a component of MCIS). There is prior research on the vulnerabilities of ADS-B both in the authenticity and integrity of messages. There could be more focus on how different attacks could affect the MCIS in different ways other than DoS. There is a mention of Arbitrary Code Execution (ACE), but it is not explored.
- Solutions are presented in the discussion section. However, the paper itself does not provide any new solutions; instead, it refers to other solutions presented in other works and states the majority of those solutions would not work for the real-time attacks they have experimented with.

### Points of interest

##### Attack description
To perform the attack, they create an attack payload in Python. This attack payload is then given to the GNU radio companion, which produces the IQ values. These are the basis of complex RF signal modulation and demodulation and are also called quadrature signals. The next step is to broadcast these signals via a transmission-enabled SDR (software-defined radio). The signal is then received by the MCIS through the ADS-B receiver, which is in communication with the EFB application, possibly allowing the attacker to gain control over the MCIS.
##### Evaluation Results
The DoS attacks they experimented with sought to affect the availability of the system, overloading it with bursts of messages. In their experiments, depending on the configuration, they saw application crashes, clogged applications, unresponsive, and not affected applications. However, for the applications which seemed to be not affected, there were valid message drops. This behavior would be inadequate for mission-critical systems.
##### Correlation between Fuzzing and DoS
Lastly, they also performed fuzzing testing on the communication between the MCIS devices and the EFB, which was done through unsecured WiFi. The use of malformed inputs showed that the applications which were vulnerable to DoS attacks at the ADS-B level were also vulnerable to fuzzing attacks. There were a couple of exceptions only. 


### Questions for discussion

1. One of the proposed solutions involves HMAC; this solution has the setback of having to disable CRC checks. Is this the only reason it is not implemented? How hard is it to implement these changes into ADS-B?
2. What other kinds of attack vectors could be possible through RF? The paper claims system crashes are one step away from Arbitrary Code Execution? Range of attacks based on RF signals?
3. Could mitigation mechanisms be present at the EFB level?

## See also

- [ADS-BSec](https://www.sciencedirect.com/science/article/pii/S2405959517302783)
- [RF attacks](https://www.trendmicro.com/vinfo/dk/security/news/vulnerabilities-and-exploits/attacks-against-industrial-machines-via-vulnerable-radio-remote-controllers-security-analysis-and-recommendations)

## Comparison

This publication is entirely out of the scope of my research work as I focus on distributed systems and data partitioning.
