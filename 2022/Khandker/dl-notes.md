# Paper Notes
* **Title:** On the (In)Security of 1090ES and UAT978 Mobile Cockpit Information Systems—An Attacker Perspective on the Availability of ADS-B Safety- and Mission-Critical Systems

* **Authors:** Syed Khandker, Hannu Turtiainen, Andrei Costin, Timo Hamalainen

* **Reviewer:** DL

* [Link to publication page](https://ieeexplore.ieee.org/stamp/stamp.jsp?arnumber=9749067)


## Contribution

* Surveyed the potential DoS ADS-B attacks, results, and proposed mitigations.
* Testing framework on the availability and resilience against DoS attacks on ADS-B technology, with a wide coverage of ADS-B transceivers, software-defined radios (SDRs), and (electronic flight bag) EFB applications, targeting the two different possible implementations of ADS-B (UAT978 and 1090ES).
* The evaluation performed using the testing framework shows that many mobile cockpit information systems (MCISs) using ADS-B crashed, leaving the door open for the attacker to execute their own code on the machine.


## Strengths

* It is very insightful to warn about the danger of using ADS-B in satellites and uncrewed aerial vehicles.
* The DoS attacks' effects are well summarized in Tables 4 and 5, with the effects being clearly differentiated according to their potential damage.


## Weaknesses

* Too many acronyms can confuse and bore people at the beginning.
* Maybe start with saying the potential catastrophes resulting from these vulnerable devices to motivate the user. Maybe they should place the Related Studies before the more technical Background. The use case is good, but it is not very well highlighted at the beginning.
* There could be a discussion on the feasibility of these attacks in the Results and Evaluation section. The danger and potential of these attacks on real-world aircraft are unquestionable. However, the setup described in the paper does not sound transposable to a real-world scenario. 


## Points of interest

* They bring up a very relevant problem beyond cybersecurity: how attempts to reduce the cost of aircraft operation can increase the attack surface of a transport regarded as very safe.


## See also

*[The following paper gives a broader review on the state-of-the-art of security in aircrafts, "Cyber security challenges in aviation
communication, navigation, and surveillance",](https://reader.elsevier.com/reader/sd/pii/S0167404821003400?token=000260BCB53609FF09D50C0C3D20DA2869B269BB18FC4EA471D981BC3500CAF954F6C6691CA6EA60C28A21BAEADCF328&originRegion=us-east-1&originCreation=20220513105803)


## Comparison

* My work involves detection and mitigation against DoS attacks on the Tor network and the possible application of those techniques to other networks, so this paper gives me a wider perspective of other situations where DoS attacks can be applied.


# Questions

1. Are there possible consequences in the scope of attacks with no effect? For instance, is there a possible consequence of a significant amount of valid messages being dropped, such as delayed updates to the location of other aircraft? Why were situations with this note regarded as "No effect"?

2. How does the experimental setup emulates a realistic aircraft under attack scenario? It is mentioned "using low power, placing the receivers and transmitters in close proximity, and employing signal attenuators", but why this setup?

3. Is there some kind of legislation or quality control that sets a baseline to what is considered secure to be used in aircraft? Are the EFB applications verified by some legal entity, or is there a quality seal since they are readily available on Google Store? How can someone responsible for the aircraft choose the most appropriate EFB application?
