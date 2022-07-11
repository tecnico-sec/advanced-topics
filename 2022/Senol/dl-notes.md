# Paper Notes
Title: Leaky Forms:
A Study of Email and Password Exfiltration Before Form Submission

Authors:Asuman Senol, Gunes Acar, Mathias Humbert and Frederik Zuiderveen Borgesius

Reviewer: DL

Link: https://www.usenix.org/system/files/sec22fall_senol.pdf


## Contribution
Since major browsers started to block third party cookies and trackers, email is a good alternative to track users. It is possible to collect users emails from forms even without the users submitting it. This motivates the study described in this paper to know whether online trackers abuse information in forms, such as user emails or passwords.

The authors investigated leaked emails and passwords in forms before submission on the 100000 top accessed websites. They evaluated how factors such as user location (US and Europe), consent mode (no-action, accept-all and reject-all) and browser configuration (desktop and mobile) affect the leaked information. This is accomplished by extending a crawler to automatically fills email and password fields in forms, monitors possible leaks in the network traffic and scripted access to input fields. With the results obtained, they contacted the entities involved in leaks and motivated two bug fixes that prevent those leaks. They also develop a proof-of-concept browser extension that detects sniff and exfiltration attempts.


## Strengths
* The related work in Section 2 is concise and well organized into four categories, making it easier for a nonexpert in browser security to follow. There are also relevant references to previous studies across the rest of the paper.

* Detailed and clear description of the process conducted to find the leaks, easy to follow and descriptive of what motivated their implementation choices in the crawler. The authors provided a step-by-step description in Section 3, making the experiment transparent and replicable.

* Even though only two locations were tested (US and Europe), this example reveals the impact of GDPR in avoiding leaks in Europe and a further discussion of the implications of the found email leaks in GDPR compliance is conducted in Section 5. This is very relevant to this study to understand how legislation can effectively motivate the protection of users' privacy online and what still needs to be done.

* Section 8 provides a good list of countermeasures against email exfiltration, testing several solutions provided by major browser vendors, as well as research solutions, using their previous techniques and results.


## Weaknesses
* The solutions presented by the authors depend heavily on the algorithms used and manual analysis, which might mean that this study is too hard to reproduce and can also miss leaks, which they discuss openly in Section 8.

* Several of the presented results distinguish between the consent modes, but there is almost no discussion about the implications of each one. This distinction was disregarded by the authors, for instance, in Table 6, where the legend says that the results were obtained using the no-action mode only. In Section 4.4, the authors write a small paragraph about the implications of the consent, but it is unclear and subjective.

* Including the mobile experiment did not add anything to the paper. The results discussed in Section 4.5 seem to be inconclusive and further evaluation of the mobile scenario should be left for future work. The crawls done with desktop and mobile were performed in significantly different periods considering webpages are very dynamic. Presenting only the desktop case would be less confusing and extensive on the paper.


## Points of interest
* Table 4 presents the top ten websites where the email was collected by a tracker before form submission and the website category, showing that Facebook, news and medical news websites appear high on the list.

* Section 5 gives a brief explanation of what GDPR is and shows how email exfiltration does not comply with GDPR in multiple ways.

* Section 7 presents a useful overview of the privacy solutions presented by popular browser vendors and states whether they avoid email leaks or not.


## See also
* Crawler source code, LeakInspector source code, follow-ups, Leaks to Meta (Facebook) & TikTok and more results to complement the paper: https://homes.esat.kuleuven.be/~asenol/leaky-forms/

* Many top global websites found to collect, leak email IDs and even passwords: Report: https://indianexpress.com/article/technology/tech-news-technology/many-top-global-websites-found-to-collect-and-leak-email-ids-and-even-passwords-report-7920519/

* An Analysis of Private Browsing Modes in Modern Browsers: https://www.usenix.org/legacy/event/sec10/tech/full_papers/Aggarwal.pdf


## Comparison
* This work compiles several techniques used in browser security, which can be very interesting to complement my research in the future, such as crawling the web and bypassing CAPTCHA mechanisms.


# Questions
1. In section 4.2, in the experience where the authors reveal that some websites using Yandex Metrica's session recording feature leak user emails, they also mention that it could be associated to the usage of the React framework. In your opinion, what could websites do to prevent leaks caused by these widely used frameworks?

2. Why did the authors focus only on email collection before form submission when it comes to sharing the emails to third parties?

3. How do you think this study can improve the transparency in online tracking, such as which third-parties are receiving users' emails?