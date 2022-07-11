# Comments on _paper-3_

Title: _Examining the Efficacy of Decoy-based and Psychological Cyber Deception_

Authors: _Kimberly J. Ferguson-Walter, Maxine M. Major, Chelsea K. Johnson, Daniel H. Muhleman_

Reviewer: _PO_

[Link to publication page](https://www.usenix.org/conference/usenixsecurity21/presentation/ferguson-walter)

## Contribution

_What are the major issues addressed in this publication?_

- Attackers are able to break into systems by running a bunch of tools and observing how systems answer to these tools. While new attacks and new defenses keep raising the bar from a security perspective, little to no work studied how deception can play a critical role in a defensive scenario by affecting the behavior of attackers, making them waste more time or be more cautious.


_What are the main contributions?  (as stated by the authors)_

- Authors devised a controlled experiment to study how the presence of decoys in a system and whether attackers are aware or not about such presence (truly or not) can affect their behavior: by delaying, deterring or disrupting attacks.
- Authors investigate 4 hypotheses on whether decoys and cyberpsychology are effective as cyber defense.

### Strengths

_In your opinion, what are the strengths of the publication?_

- Authors make an extent evaluation of how decoys and cyberpsychology can affect attackers, being the first (or one of the first) paper that performs such kind of study
- Real live study with many experts (acting as attackers) in different conditions make the results to be statistically valid
- A lot of datapoints collected: keylogs, network traffic, attackers' findings (during and after the study), screen captures/recordings, IDS alerts using traffic captures and decoy alerts.
- For different types of attacker progress the authors correlate the observed results with the hypotheses that supports such results (number of targets that were attacked supports the hypotheses that "deception is effective even if the attacker is aware of its presence"; attackers unaware of deception made more progress supporting hypotheses that "defensive cyber tools and psychological deception impede attackers who seek to penetrate
computer systems and exfiltrate information"; ...)

### Weaknesses

_In your opinion, what are the weak points in this publication?_

- Some terms that are used along the paper are not properly explained making it difficult to follow along for outsiders of the area: red teamers, cyber attack stages (reconnaissance, weaponization, delivery, ...), ...

### Points of interest

- Examples or scenarios
  - Participants unaware of decoys take less time to target their first system
  - Participants that didn't face decoys are more likely to retry a failed exploit attempt
  - Participants that didn't face decoys reported more attack successes
  - More participants that didn't face decoys were able to exfiltrate more information from their targets compared to participants that faced decoys  
  - Participants that didn't face decoys registered more keystrokes
  - Participants unaware of decoys took more time to initiate an interaction with a decoy
  - Less bytes were sent to real systems in which decoys were also available in the network
  - Perception is different in each condition (Decoy Present/Absent and Attacker Informed/Uninformed) - less reported attack failures in Absent/Uninformed and Present/Informed; more participants considered the network secure in the Absent/Informed and Present/Uninformed



## See also

- [The Tularosa Study: An Experimental Design and Implementation to Quantify the Effectiveness of Cyber Deception](https://www.osti.gov/servlets/purl/1524844)

### Questions for discussion

1. From this study it looks like having the attacker aware of the presence of decoys affects its behavior... However attackers that were not aware were able to make more progress... On a real live system, how can an attacker know if there are decoys or not? How can a company affect the attacker behavior? How does this study translate to live systems?

2. From this study it looks like decoys are able to affect attacker behavior... So does that mean that real products should "mimic fake vulnerabilities" so that attackers wastes time trying something that will lead them to nowhere on real products? Or companies should place dumb nodes in their networks?

## Comparison

_Is this work relevant for your work?_ No
