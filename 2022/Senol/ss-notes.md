# Comments on _Paper 2 notes_

Title:  Leaky Forms: A Study of Email and Password Exfiltration Before Form Submission

Authors: _ Asuman Senol ,  Gunes Acar , 	 Mathias Humbert ,  Frederik Zuiderveen Borgesius_

Reviewer: _reviewer initials_

[Link to publication page](https://www.usenix.org/conference/usenixsecurity22/presentation/senol)

## Contribution

_Advertisers, data brokers, and marketing and analytics companies use email addresses or derived identifiers for cross-site, cross-platform, and persistent identification of individuals and, by extension, to monetize content for their clients. The use of scripts that monitor and capture keystrokes when the user is filling a form.
The author wrote this article mainly because users who type their email addresses and passwords in the forms on the sites, and even if they do not submit the form, this information is collected by third-party scripts for advertising and commercial purposes. 
Web sites To monetize their users' information, such as email,  in most cases without the user's consent, provide information to companies. 
This problem has been studied in the European Union and the United States and has achieved exciting results. In this project, the author uses several extensions in the browser to determine what percentage of selected sites in the E.U. and the U.S. do so.
GDPR law has been an issue in  European Union since 2018, and any processing of users' information is prohibited, and there are many penalties. However, despite this law, some sites do not pay attention to it and continue collecting user information and providing it to a third party. According to this law, any company with a business relationship with the European Union must follow this law.
However, due to the lack of law in the U.S., the percentage of customer information collected by third parties is higher._

### Strengths

_Collecting emails by third persons without submitting a form and making money from this issue by sites is unacceptable. Exploring and discovering sites that do this can be very important and constructive.
In my opinion, one of the strengths of this project is its implementation in the real world and testing its working method on most available top sites. It has also conducted the test in two regions of the European Union and the U.S., one with strict GDPR rules and the other without rules.
Another thing that fascinated me was the citation of the results. It means that the results obtained from the testing of websites are accurate and reliable._

### Weaknesses

_
- Given the problems and weaknesses mentioned by the author at the end of the article, I think one of the weaknesses of this article is the lack of technical explanations about TRC and how it works. No technical or programming description has been given throughout the article about this plugin. Only its name and a few other plugins used alongside it was mentioned. It would have been better if they had explained the technical performance and the changes they have made.

- LEAKINSPECTOR currently only uses DuckDuckGo's blocklist._ 

### Points of interest

- _The study sampled 100,000 highest-ranking websites. Of the 2.8 million web pages analyzed using a crawler based on DuckDuckGo's Tracker Radar Collector tool, 1,844 websites allowed trackers to exfiltrate email addresses irrespective of the 'submit status' of the entered data when visited from Europe.

When the researchers visited the same websites from the U.S., they found 2,950 websites that allowed data exfiltration, 60% more than in Europe._

- The author performed this experiment with two desktop and mobile devices; the results differed. The results show that the number of sites that collected data on desktop devices is more than mobile. 



### Questions for discussion

1. If a website did block the Crawlers, can TCR check it? Moreover, if not, what is the solution?
2. Is there a difference between HTTP and HTTPS requests when checked by the LEAKINSPECTOR? LEAKINSPECTOR can check HTTPS requests?
3. In a form as a pop-up window, can it also check or not?

## See also

- [link to related publication](https://complexdiscovery.com/embracing-differences-interplay-of-digital-forensics-in-ediscovery/)
- ...


## Comparison

_This article is not related to my field of study. In some ways, however, the study suggests that despite the GDPR, privacy may still be violated, and user information may be processed and used._

_My research is in the field of IoT security._
