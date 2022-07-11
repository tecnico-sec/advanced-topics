# Comments on _paper-4_

Title: _Online Website Fingerprinting: Evaluating Website Fingerprinting Attacks on Tor in the Real World_

Authors: _Giovanni Cherubin, Rob Jansen and Carmela Troncoso_

Reviewer: _PO_

[Link to publication page](https://www.usenix.org/conference/usenixsecurity22/presentation/cherubin)

## Contribution

_What are the major issues addressed in this publication?_

- Previous work in Website Fingerprinting at TOR (predict the website a user is accessing by looking to the traffic between the victim and the first TOR relay node) is questionable and unrealistic: rely on fixed synthetic data that may be outdated and not adapt to changes. Authors address this issue by using classifiers that rely on real traffic (traffic that leaves the TOR exit node) making the classifier adapt to network and traffic changes over time.


_What are the main contributions?  (as stated by the authors)_

- A more realistic website fingerprinting attack on the TOR network by not being performed over simulation or synthetic data but instead deployed on the real TOR network
- Website Fingerprinting classifier is trained based on real traffic that exits the TOR exit node

### Strengths

_In your opinion, what are the strengths of the publication?_

- Shortcomings of previous work is addressed
- Having a online classifier that is trained based on the traffic that leaves the exit node makes the ML model to adapt to possible network and traffic changes
- Evaluation performed by running real TOR relay nodes on the TOR network
- Evaluation addressed privacy concerns (a top requirement of TOR) since real traffic could traverse the exit node that was used in the evaluation
- Authors evaluation their solution (classifier based on traffic that leaves exit node) with previous work (synthetic data) and hybrid mode.

### Weaknesses

_In your opinion, what are the weak points in this publication?_

- Authors use "non-reversible pseudonyms (hashes)" as website labels. The evaluation takes into consideration that these non-reversible pseudonyms are good private identifiers of webpages... authors don't comment about the possibility of hash collisions which may affect their evaluation, i.e. pages that match their top 100 list may be webpages that are not actually on that list but instead their resulting hash matches one entry of this list.
- The attack evaluation was only possible to be performed at the entry node by using a custom configuration "opt-in" due to security reasons.
- Results are a bit surprising: low accuracy due to amount of data per site in the training set (due to resource constraints) and having 75 samples per website having better accuracy than 100 for the sample-1000 training set (according to the authors due to local minima problems).
- Authors should have provided more details on the ML model: how they have reached to the final classified model (did they use a validation set to fine tune the model?; what was the architecture of the model like number of layers, neurons, ...)
- TOR clients are also available for the smartphone. Websites accessed by these devices may be adapted to their screen size. No comment about such implication on the evaluation.
- More details about the evaluation should be given to in order to be sure that the evaluation was performed in a correct way, e.g.: for the monitored vs unmonitored evaluation, the authors simply say that the they divide the data and perform evaluations... did they perform this evaluation only a single time? or did they perform the evaluation multiple times over different sets of the same size and then averaged the results?

### Points of interest

- Examples or scenarios
  - As expected, performing Website Fingerprinting based on a classifier that is trained on real data has better performance compared to previous work that relies on classifiers that are based on synthetic data
  - According to the results, an attacker intending to monitor more than 25 websites is unlikely to succeed



### Questions for discussion

1. How realistic is this form of attack to happen? An attacker must have access to the traffic entering the first TOR relay node for classification purposes and of the traffic leaving the last TOR exit node for training purposes. Can anyone deploy relay nodes on the TOR network?

2. Hashes are performed on the website identity (pseudonym) due to privacy concerns. Authors don't make any comment regarding the possibility of hash collisions. Are the results realistic considering that some websites may have been classified incorrectly due to hash collisions?

## Comparison

_Is this work relevant for your work?_ Maybe. On my thesis I will need in someway to be able to perform traffic classification to distinguish benign/malicious traffic. I may explore the Triplet Fingerprinting solution that was adopted by this paper.
