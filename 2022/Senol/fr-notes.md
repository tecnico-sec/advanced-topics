# Comments on paper 2

Title: Leaky Forms: A Study of Email and Password Exfiltration Before Form Submission

Authors: Asuman Senol, Gunes Acar, Mathias Humbert, Frederik Zuiderveen Borgesius

Reviewer: FR

[Link to publication page](https://www.usenix.org/system/files/sec22fall_senol.pdf)

## Contribution

Online forms are a core component of any website with user sign-in and sign-up functionalities. While previous work focused on leaks that occur post the form submission point, this work focuses on issues that may occur before the form submission.

In order to conduct their research, the authors developed a crawler capable of detecting and filling out email fields on top websites. Additionally, the crawler can detect script access to input fields in the form. This work led to the discovery of 41 previously unknown tracker domains that exfiltrated email addresses. Furthermore, they developed a proof-of-concept browser add-on that seeks to detect and prevent the exfiltration of information through online forms.

Moreover, the paper discusses the compliance of email exfiltration through forms with the GDPR standards whilst there were also contacts between the authors and sample websites to enquire about the purpose of email collection and other policies.

Lastly, this work also contributed by detecting password collection by session replay providers on a subset of the websites under analysis. As a result of these findings, two third-party trackers updated their system to mitigate the issue.

### Strengths

- Related work clearly states how this work differs from previous work that is also focused on personal information leakage. E.g., Chandramouli et al. focus on email header injections. The paper introduces a clear novelty;
- Valid reasoning and precise explanation behind design decisions, such as how many pages the crawler should visit in its search for email fields;
- Improvements made on the work they follow up on. In particular, the leak detector implementation following Englehardt et al.work. E.g., by identifying new encodings for email and password fields

### Weaknesses

- Mobile evaluation is not very extensive. The differences between mobile and desktop crawling results are attributed to the time between experiments without any evidence of the further investigation. 

### Points of interest

The solution to email exfiltration proposed by the authors is rather interesting. This work proposes to tackle the issues identified through the usage of a browser extension. It comprises two main features:
- Sniffer Detector - This component is responsible for detecting and, if chosen, preventing the sniffing of input fields that may comprise personal data. It does so by instrumenting the browser and by leveraging the tracker blocklist deployed by DuckDuckGo.
- Leak Detector - Monitors HTTP traffic and seeks to identify leaks from the monitored fields. It also relies on blocklists.

Another interesting topic discussed in this work is the limitation list. The authors are aware of the limitations in leak detection due to the multitude of encodings/encryptions possible to mask such activities. The detection of leaks is fundamental for the formulation of blocklists. The authors discuss the limitations involved with the usage of blocklists. However, they don’t mention how both of these limitations correlate. See Q2 and Q3.

### Questions for discussion

1. Is intensive regulation through legislation such as the GDPR a solution to the presented problems, and to which extent can it complement software solutions?
2. Is there a correlation between leak detection and the quality of blocklists? The work mentions they were able to detect new tracker domains which could be added to blocklists; there seems to be a correlation
3. Would the creation of a standard blocklist help solve the issues discussed in this work? Combining the efforts by multiple different detectors and thorough verification to ensure the quality of the blocklist and thus avoiding the false positives and negatives mentioned.

## Comparison

This publication is entirely out of the scope of my research work as I focus on distributed systems and data partitioning.
