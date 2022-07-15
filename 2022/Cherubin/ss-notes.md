# Comments on _Paper 4 notes_

Title:   Online Website Fingerprinting: Evaluating Website Fingerprinting Attacks on Tor in the Real World

Authors: _Giovanni Cherubin ,   Rob Jansen , 	 Carmela Troncoso_

Reviewer: _SS_

[Link to publication page](https://www.usenix.org/conference/usenixsecurity22/presentation/cherubin)

## Contribution

Using Website Fingerprint (WF) attacks on the Tor network, hackers can guess which websites the user will visit by monitoring the connection between the user and the Tor network. This attack can also compromise users' privacy. 
The paper's primary purpose is to evaluate the effectiveness of WF attacks in the real world without compromising the security and privacy of Tor network users. WF attacks are now carried out with great precision. Are these attacks effective in the real world and the existing network with many sites or not? 
This paper tests a new Triplet Fingerprinting attack using an exit relay in the Tor network. This article examines the WF attack on the top 100 sites in terms of site rankings by Alexa.

### Strengths

Researchers typically use artificial traffic to evaluate the effectiveness of a WF attack. This synthetic traffic is tested offline on a few sites, which can not show the actual efficacy of this attack. 
However, the author of this article has used a Triplet fingerprint attack on the Tor network exit relay and in the real-world Tor network. It has also increased the scope of its surveyed sites to 100 in the real world and 1,000 in the artificial state.


### Weaknesses

One of the weaknesses of this experiment is the short duration of the one-week review, which is spent on evaluation, which seems to change over time as the results are obtained.
As mentioned in this article, a hacker can successfully use a WF attack by examining fewer sites in the real world. However, this article does not offer any solution to this attack and only mentions that this attack can happen on the Tor network.

### Points of interest

- Investigate a real-world attack and its effectiveness_
- Since users use the Tor network to protect their privacy, hackers may still attack privacy. Even the Tor network does not prevent users from hiding when using the Internet, and hackers can guess the sites users visit._

### Questions for discussion

1. Studies have shown that hackers can succeed in this attack by selecting a small number of websites; what is the solution to prevent this from happening?

## See also

- [link to related publication](https://www.researchgate.net/publication/290568676_A_Critical_Evaluation_of_Website_Fingerprinting_Attacks)
-[link to related publication](https://www.researchgate.net/publication/305423586_On_Realistically_Attacking_Tor_with_Website_Fingerprinting)


## Comparison

By studying this article, I have concluded that only laboratory experiments can not obtain accurate results in my work. It is better to test my work in natural environments with accurate data._

I also found that cyber attacks have to be viewed from different angles; each cyber attack can be executed differently. To investigate IoT and its security, attacks that may occur on the IoT network should be examined differently. For example, the WF attack uses an input relay as an age in this article. However, the author suggests using the Tor network output relay to get a better result.
