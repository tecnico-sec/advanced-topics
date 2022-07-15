# Comments on 02

Title: "Leaky Forms: A Study of Email and Password Exfiltration Before Form Submission"

Authors: Asuman Senol, Gunes Acar, Mathias Humbert, Frederik Zuiderveen Borgesius

Reviewer: RS

[Link to publication page](https://www.usenix.org/conference/usenixsecurity22/presentation/senol)

## Contribution

The leakage of private information on the web is a great issue for both users, in terms of security and privacy, and web domains, as they must comply with privacy regulations such as the GDPR. Leaky Forms focuses on data leakages __before__ data submission on websites, where most users have yet to consent to the use of their data by third parties.

The main contributions of this work include a study and analysis on data leakage before data submission, including email and password information, across 100,000 of the top accessed websites, a crawler implementation focused on measuring exfiltration of email and passwords, and the GDPR compliance of such exfiltrations.

### Strengths

* Extensive study of the most widely used websites, using multiple relevant configurations and environments.
* Complete and in-depth implementation of the leakage crawler, improving and extending previous work on leakage detection.

### Weaknesses

* While the work makes an effort to motivate that form abandonment is an issue, the presented statistics may mislead its importance. While some users report that they have abandoned forms, most of the forms will most likely be submitted. The study lacks a direct comparison against leakages after submitting forms.
* The paper often contradicts its own findings and methodologies, making it confusing to understand their impact and scope.
* A more in-depth analysis of __how__ and __where__ the data is leaking from websites is missing, which would be useful for security improvement.
* While the authors provide some form of countermeasure against these leakages, its effectiveness is questionable, as no experimental evaluation is shown, and there is no mention of its impact on website functionality.  

### Points of interest

- The study encompasses various scenarios, including diversity in websites, continents, and environments.

- Website characterization includes surprising results in EU environments, both in terms of lack of consent requests and relatively high amount of leakage in cases where consent is __not given__.  

### Questions for discussion

1. How prevalent are pre-submission leakage compared to post-submission leakage? Would systems that are affected by one likely to be affected by the other?
2. Would pre-submission leakages on logins go against the GDPR if consent was given during registration?
3. Does the blocking of the countermeasure tool affect website functionality? If so, how would this blocking take into account the user consent to avoid affecting functionality?

## See also

- [Are You Sure You Want to Contact Us? Quantifying the
Leakage of PII via Website Contact Forms](https://petsymposium.org/2016/files/papers/Are_You_Sure_You_Want_to_Contact_Us__Quantifying_the_Leakage_of_PII_via_Website_Contact_Forms.pdf)
- [No boundaries: data exfiltration by third parties
embedded on web pages](https://webtransparency.cs.princeton.edu/no_boundaries/assets/no-boundaries-pets2020.pdf)

## Comparison

Study-based works like this paper significantly differ from my own system-based work, especially regarding the scientific outcome of the work. While system-based works focus on developing a solution and experimentally evaluating it compared to the state-of-the-art, studies focus on a __problem__, analyzing its sources, impact, and coverage. Studies are the first step in the scientific process, defining the problem for a later solution and system to be developed.
