# Comments on P4

Title: "Online Website Fingerprinting: Evaluating Website Fingerprinting Attacks on Tor in the Real World"

Authors: Giovanni Cherubin, Rob Jansen, Carmela Troncoso

Reviewer: RS

[Link to publication page](https://www.usenix.org/system/files/sec22summer_cherubin.pdf)

## **Contribution**

Website fingerprinting (*WF*) attacks on the Tor network can deanonymize users. However, the attack reliability in a real-world scenario is yet to be proven, with current work only considering synthetic datasets.

The main contribution of this work is the first real-world evaluation of *WF* attacks in the Tor network, including:

- A new threat model based on real Tor traffic
- A new method for training safely on genuine Tor traffic, taking in consideration the required ethical considerations
- An in-depth evaluation of the model, comparing the efficacy of models trained on synthetic and real data

### **Strengths**

- The work goes to great lengths to protect Tor users' privacy while being able to extract real-world data.
- The monitored site selection methodology is a compelling selection of a real-world scenario, with its consistency being proven in Figure 3. a.

### **Weaknesses**

- Some of the current limitations regarding synthetic Tor traffic generators seem to be easily managed.
- The authors utilize a synthetic crawler as a client, which, as the authors mention for synthetic workloads, can make traffic easier to predict and greatly goes against the work's motivation and skews the evaluation.
- The evaluation lacks some explanation about the machine-learning terminology (precision, recall).
- The presented results introduce severe doubts about the reliability of the model. The results are extremely volatile depending on the chosen set, as seen multiple times in Figures 4, 6, and 9. A relation between easily fingerprinted websites and the website's popularity is required to understand the impact of fingerprinting truly.

### **Points of interest**

- The authors mention multiple limitations regarding Tor synthetic traffic generators and the inability to test on entry relays. Using this work and the developed model as a basis, a set of future works on improving Tor's synthetic traffic generators is the natural next step.
- Due to clients' privacy concerns, multiple obtained results are left without a concrete and reasonable explanation. It would be interesting, and for better security analysis, creating a middleware where data can be safely obtained without compromising privacy may be necessary.

### **Questions for discussion**

1. Based on the obtained flows from an exit relay, wouldn't it be able to create a more realistic traffic simulator? Arent, are any limitations like concept drift easily to overcome with constant data intake?
2. The authors seem to downplay the effectiveness of WF due to the effectiveness only on small-sized sets. Do you share this vision? Wouldn't WF attacks mainly be used to deanonymize access to specific websites?
3. While the model may falter with the increase in monitored sites, would not running multiple instances of the model monitoring different websites circumvent this problem?

## **See also**

- [A Critical Evaluation of Website Fingerprinting Attacks](https://dl.acm.org/doi/10.1145/2660267.2660368)

## **Comparison**

One major issue that has come to light when publishing on consistency topics (especially w.r.t more recent consistency levels like Transactional Causal Consistency) is the real-world application and use-cases. While we can find specific use-cases, having real-world data that would corroborate the need for these consistency requirements would make our work easier to sell.

The need to obtain real-world data while maintaining its privacy and anonymity is a real problem, not only in anonymous communication networks, as major companies like Amazon, Facebook, and others are reluctant to share their system data due to its marketing value. Building a framework for secure and anonymous data collection could incentivize significant companies to share their data.
