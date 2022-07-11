# Paper Notes
Title: Online Website Fingerprinting: Evaluating Website Fingerprinting Attacks on Tor in the Real World

Authors: Giovanni Cherubin, Rob Jansen, and Carmela Troncoso

Reviewer: DL

Link: https://www.usenix.org/system/files/sec22summer_cherubin.pdf


## Contribution
There are several website fingerprinting attacks on Tor to determine the websites being accessed by users, claiming to offer high accuracy. However, these attacks are performed on synthetic traffic, accessing a small subset of websites, using automated crawlers, and are dependent on the time in which the traffic captures were collected. These factors may compromise these attacks' applicability to real world traffic. If these attacks prove to be successful, countermeasures should be implemented by Tor to ensure its users' privacy. 

The authors aim to test the effectiveness of website fingerprinting attacks on Tor using real world Tor traffic, demonstrating whether such attacks represent a real threat to Tor users' privacy. To achieve this, they use novel machine learning techniques (Triplet Fingerprinting attack) and collect network data privately at Tor entry and exit relays. This study proved that accuracy gets significantly lower in real world scenarios where the attacker wants to monitor a significant number of websites and also depends on the website's fingerprintability.


## Strengths
* Wide coverage of the limitations of state-of-the-art website fingerprinting attacks on Tor, which is also applicable to other traffic correlation attacks on Tor.

* Ethical considerations when capturing real world Tor traffic in exit nodes that could compromise users' privacy. Full disclosure to the Tor Safety Board and novel technique to obtain ground truth information. This information is usually obtained using synthetic traffic in other studies on Tor. But this study used a modified Tor version that includes a non-reversible hash of the accessed website, generated with a temporary key, included in the packets, that is later recognized by the entry nodes.

* Detailed Results Section and clear separation of conclusions into paragraphs. For instance, "Dependance on the Number of Training Traces" and "Dependance on Monitored Set Size".

* Taking into account the diversity of websites in website fingerprintability, less commonly accessed websites, the number of monitored sites, and the distortion from entry to exit relays, which are relevant factors that are overlooked many times, even in other related studies.


## Weaknesses
* The description of related work on fingerprinting attacks on Tor is very short.

* Does not detail why website fingerprinting attacks are generally conducted in the entry relay, even though that is mentioned multiple times.

* Authors do not explain the measures used in the Evaluation Results section.

* Figure 5 is confusing. On the figures on the right, the accuracy starts by decreasing, which is described in the text as well, but that does not happen on the figures on the left.

* Despite being a relevant study, there's no significant resulting "product" from this paper. It is still very hard to capture real-world traffic, even for research that aims to improve the privacy provided by Tor. The ethical implications are still a big hurdle, even using the techniques described. A more practical approach would be to provide suggestions on how to improve synthetic datasets to make them as close as possible to real world traffic.


## Points of interest
* Figure 8 shows the impact of the monitored set size on the attack's performance. 

* Figure 10 shows the distortion that happens to traces between exit and entry relays.

* Triplet Fingerprinting attack description in Appendix.


## See also
* Triplet Fingerprinting: More Practical and Portable Website
Fingerprinting with N-shot Learning: https://dl.acm.org/doi/pdf/10.1145/3319535.3354217

* Attacks on Tor: https://github.com/Attacks-on-Tor/Attacks-on-Tor

* Researchers Demonstrate New Fingerprinting Attack on Tor Encrypted Traffic: https://thehackernews.com/2021/11/researchers-demonstrate-new.html


## Comparison
This paper was very insightful on all the factors that can make synthetic datasets produce unrealistic results, as well as the plethora of ethical concerns that we need to have present when capturing real world traffic. Since my current work is also about attacks on Tor, I have to produce synthetic datasets to evaluate the attacks and think about all the ethical implications that may arise from them, thus this was very relevant to make me question my methodology and results.


