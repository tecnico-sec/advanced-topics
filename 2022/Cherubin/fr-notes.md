# Comments on paper 4

Title: Online Website Fingerprinting: Evaluating Website Fingerprinting Attacks on Tor in the Real World

Authors: Giovanni Cherubin, Rob Jansen, Carmela Troncoso

Reviewer: FR

[Link to publication page](https://www.usenix.org/system/files/sec22summer_cherubin.pdf)

## Contribution

Website Fingerprinting attacks introduce a security risk for any user that seeks to keep their online endeavors anonymous. State-of-the-art fingerprinting techniques rely on machine learning classification aided by data collected from network traffic. Previous research conducted on the Tor network relied on data collected at or prior to the entry relay.
The results presented by previous studies rely on synthetic traffic generation obtained through the use of crawlers running on popular URL lists. This approach circumvents the impossibility of collecting ground truth regarding the websites visited by Tor users at the entry relay level. However, this methodology does not mimic user behavior and imposes restrictions on the websites studied.
Another limitation of previous work is known as concept drift. Both training and evaluation data are often collected in the same period. As a result, this approach fails to adapt to real changes in the traffic patterns over time.
This work seeks to contribute with a new technique to evaluate the feasibility of website fingerprinting attacks in the real world whilst avoiding the aforementioned pitfalls. To achieve this, they propose accurately collecting data at an exit relay. By using genuine and synthetic traffic, they can compare both approaches. Lastly, they contribute with a threat assessment of a website fingerprinting attack on real Tor users.


### Strengths

- Instead of attempting to avoid previous limitations inherent to synthetic data through improvising browsing models or more extensive data sets, this work introduces a novel adversarial model that does not incur in modeling the user behavior.
- Running a Tor entry or exit relay can incur several risks due to the nature of the network and its known uses. The precautions taken (e.g., through pseudonyms on websites) are worth mentioning as the value of the work and the data models produced could prove dangerous if compromised.

### Weaknesses

- The authors start by stating that their newly introduced adversary would be capable of observing the websites AND webpages that Tor users visit. However, later on, they state that due to TLS, they can online determine the website and not the particular webpages.
- Security limitations hamper many experiments. The same limitations apply to previous work, which could have followed different approaches if said limitations were not relevant in their context.

### Points of interest

The results demonstrate that website fingerprinting attacks are only successful in the real world if the adversary aims to identify websites within a limited pool. The rapid decay in accuracy as the number of monitored websites increases backs this claim. See Q1.

As discussed above, a big weakness of this work is their limitation due to TLS encryption in the traffic from the exit relay to the network. They cannot target individual web pages by leveraging real traffic as previous work does. As a result, in the presence of any website using HTTPS, it will not be possible in this study to perform fingerprinting to its full scale at a web page level. Stripping the TLS layer is also not an option due to Tor policies (see Q2).

Lastly, they propose introducing systems capable of performing website fingerprinting analysis without compromising user privacy. It is an exciting idea. However, there is no further elaboration on the topic, and the reference provided is for a paper a couple of decades old.


### Questions for discussion

1. Are targeted website fingerprinting attacks a more significant cause for concern than nontargeted ones? Attacks are generally conducted on particular targets; this study proves that it is an effective attack to that extent.
2. On exit relays, should Tor deploy measures that seek to verify who is running Tor exit relays? Moreover, can Tor identify rogue exit relays? See link below
3. On the technical side, what are possible defense strategies for the introduced attack model? Padding between client and middle relay is introduced as a solution, but it is a known overhead problem in Tor networks, especially for mobile devices.

## See also

- [link to related publication](https://blog.torproject.org/bad-exit-relays-may-june-2020/)

## Comparison

This publication is entirely out of the scope of my research work as I focus on distributed systems and data partitioning.
