# Comments on _paper-2_

Title: _Leaky Forms: A Study of Email and Password Exfiltration Before Form Submission_

Authors: _Asuman Senol, Gunes Acar, Mathias Humbert, Frederik Zuiderveen Borgesius_

Reviewer: _PO_

[Link to publication page](https://www.usenix.org/conference/usenixsecurity22/presentation/senol)

## Contribution

_What are the significant issues addressed in this publication?_

- Cookies have been a great way to track users online in the past. However, cookies are limited to the web, making their utilization not possible outside the web (e.g., on smartphone apps); also, more recently, browsers have started blocking third-party cookies and trackers. This motivated third-party ad trackers to start using email addresses as global identifiers to track users. This paper studies to what extent third-party trackers collect email addresses (and passwords) when users fill a form and do not submit it. This paper studies this email/password leaking in different locations, consent modes, and device types.


_What are the main contributions? (as stated by the authors)_

- Authors developed a crawler capable of detecting email and password fields and intercepting scripts that access such fields; a browser add-on was also developed in order to alert users of such type of interception. All the results obtained from the crawler are exposed on the paper showing that thousands of pages collect email addresses before submission; passwords were also collected by around 50 providers.

### Strengths

_In your opinion, what are the strengths of the publication?_

- Good related work
- Detailed explanation of how the crawler works: how it finds login/register pages; how it identifies email/password fields; how it fills such fields in order not to be perceived as a bot.
- Evaluation performed on over 100K websites
- Manual analysis uncovered 41 tracker domains that were not on public tracking lists
- Evaluation spanned several configurations: location (EU/US), consent mode (no-action, accept-all, reject-all) and device type (desktop/mobile) over different time intervals.
- Authors list the top trackers uncovered by the crawler and whether they leak each key pressed by the user, whether the email is sent in clear-text/hashed/encoded
- Authors shared their findings with all parties found by the crawler
- Authors verified that existing countermeasures in Firefox and Safari do not protect email exfiltration again
- A browser extension named LeakInspector was developed capable of warning users about sniffing events and blocking requests containing personal data
- All code is publicly available

### Weaknesses

_In your opinion, what are the weak points in this publication?_

- In the introduction, it is referred that "We fit the crawler with a pre-trained machine learning (ML) classifier that can robustly detect email fields." Little to no information about how the ML model was built: what form of the model was used (logistic regression/neural network/...), what features were used in training, ...

### Points of interest

- System characteristics, assumptions
    - Crawler capable of finding forms
    - Different settings possible: consent mode and device type
    - Crawler executed from different locations


- Evaluation data sets
    Website Ranking:
      - [Tranco Website Ranking](https://tranco-list.eu/)
    Domains owned by companies:
      - [Tracker Radar's entity list](https://raw.githubusercontent.com/duckduckgo/tracker-radar/main/build-data/generated/entity_map.json)
    Trackers' list:
      - [Disconnect](https://github.com/disconnectme/disconnect-tracking-protection)
      - [Whotracks.me](https://whotracks.me)
      - [DuckDuckGo](https://staticcdn.duckduckgo.com/trackerblocking/v2.1/tds.json)
      - [uBlock Origin](https://github.com/gorhill/uBlock)
    Paper code:
      - [LeakyForm](https://github.com/leaky-forms)


### Questions for discussion

1. Are privacy regulations based on the users' location, servers' location, or both? If I am in Europe and I access a service that is hosted both in Europe and the US, if I use TOR and my request is redirected to the US server, if there is a leak of my personal data, is there a violation of Europe or US law?

2. Providers typically store a lot of data in order to protect themselves (e.g., from cyberattacks). According to the paper, GDPR applies when personal data (including IP addresses) is processed. Does this mean that providers can only store this information if the attacker allows the provider to process personal data? If the provider stores such information without consent, is it violating GDPR?

## Comparison

_Is this work relevant to your work?_ No
