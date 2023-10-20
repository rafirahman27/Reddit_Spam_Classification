# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png) Project 3 - Reddit Web APIs & NLP
---
# Spam Filtering and Spam Classification
---
Scammers are a pervasive problem not just on Reddit but all aspects of our lives, with users of all experience levels falling victim to them. With these individuals deploying a variety of tactics to  deceive their targets, including phishing emails, fake websites, and social engineering.<br>
<br>
Working with the people behind Scammer Payback youtube channel, the goal of this project will be able to create 2 models, utilising data scrapped from Reddit;<br>
<br>
1) Model 1 will filter through the data classing them as Scam or not Scam
2) Model 2 will categories the Scam post into Phishing or Malware to identify what tactic the scammer is using 
---
# Research
---

Scams can have a significant impact on victims, both financially and emotionally. Victims may lose money, have their personal information stolen or even be blackmailed. These scammers will deploy multiple different strategies and wait for innocent people to fall into their traps.<br>
<br>
Phishing techniques will consist of the con artist using, emails, texts or phone calls to trick users into providing them with their personal details, which they will use in multiple different ways to get money from the victims. The UK's National Cyber Security Centre reported that "as of September 2023 the number of reports received stands at more than 24 million".<br>
<br>
With Malware the goal is to install an application/virus or another form of spyware onto your device that will give the swindler access and the ability scavage your information, potentially without even engaging with you. Along with taking your information, this method of scam can also lead to your device slowing down, have excess amount of blotware being added onto your system and cause an excessive amount of pop ups. 

---
#### Citations
https://www.ncsc.gov.uk/collection/phishing-scams
<br>
https://consumer.ftc.gov/articles/how-recognize-remove-avoid-malware

---
# Data Dictionary

The dictionary below with cover the format of the 2 dataframes used before any preprocessing techniques where applied.

---
|Feature|Type|Dataset|Description|
|---|---|---|---|
|created_utc|*float*|1.697589e+09|Time stamp of when post was scrapped|
|title|*string*|Is my friend about to be scammed?|title of the post|
|self_text|*string*|Friend of mine from back in Uni (before we mov..|Main text of the post|
|Subreddit|*string*|Malware| The subreddit the post was scrapped from |
|self_text_len|*int*|939| Number of characters within the self text|
|self_text_count|*int*|183| Number of words within self text|
|punc_count|*int*|32| The number of punctuation found in self text|

---
# Executive Summary
---

With scammers being a day to nuisance, always using different and new methods to victomize innocent and vulnerable people. Which is where people like Pierogi and his team at Scammers Payback come in, who go after these con artist. <br>
<br>
To create our model, we will be scrapping posts from subreddits, Scams, Malware, Phishing and Scam Radar, filtering them into the 2 categories of Phishing and Malware. We will also be scrapping data from Movie Reviews and Movie Suggestions and using this data as non spam data.<br>
<br>
The first model we create will look to pull in all the data and filter out the scam data from the input, this will then be taken into the 2nd model that will identify whether the scam method falls into the Phishing or Malware category. This will allow Pierogi pass the information over to the appropriate team, so that can shut down these criminals.

---
#### Citations
https://www.reddit.com/r/Scams/
<br>
https://www.reddit.com/r/Malware/
<br>
https://www.reddit.com/r/phishing/
<br>
https://www.reddit.com/r/scam_radar/
<br>
https://www.reddit.com/r/moviereviews/
<br>
https://www.reddit.com/r/MovieSuggestions/

---

# Conclusion & Recommendations
---

|Model|Train Accuracy|Test Accuracy|Correctly Predicted|Incorrectly Preddicted|
|---|---|---|---|---|
|Baseline Spam not Spam model|99.9%|99.7%|1,417|4|
|Baseline Phishing/Malware model|99.4%|74.0%|529|186|
|Model 1 Phishing/Malware model|76.8%|75.4%|539|176|
|Model 2 Phishing/Malware model|82.8%|75.5%|540|175|
|Model 3 Phishing/Malware model|91.0%|73.7%|527|188|
|Model 4 Phishing/Malware model|94.5%|74.97%|536|179|
|Model 5 Phishing/Malware model|70.96%|56.2%|402|313|

---

To conclude we was able to create our 1st filtering model with 99.7% accuracy on our test data with filtering the Scam data out of the dataset, which ended up being our baseline Logistic Regression model. <br>
<br>
Now for the Phishing and Malware categorizing model as we can see from the data above it is between Model 1 and Model 2. When diving deeper into the split of malware and phising mistakes model 1 had a 138 to 38 split, model 2 had a 127 to 48 split, whereas model 4 has a 94 to 85 split.<br>
<br>
With Malware and Phishing data being very close together, in regards to the terminology used and that this data is postings of peoples experience rather than the raw data directly from the scammer, it is easy to understand why the model was strugglying with improving it's learning process of the data and making the false predictions. In this case we have decided to go with model 4 as it was not strongly favouring one category over the other.  
<br>

1) Look to improve Model 1 by either adjusting the Logistic Regression parameters or trying other model methods, like Random Forest
2) Look to improve Model 2 by introducing email or text or etc data that is directly from scammers and see how the model reacts. 
3) Introduce Multi Classification that is able to create a 3rd category which will create a 3rd output class that will highlight data that may sit inbetween Phishing and Malware that needs more attention.
