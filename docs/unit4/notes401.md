---
layout: notes
title: "📓4.1: Ethics of Data Collection" 
parent: "4️⃣ Data Collections"
nav_order: 1
---

## Table of Contents
{: .no_toc .text-delta }

{: .fs-2 }
- TOC
{:toc}

---

{:.note}
📖 This page is a condensed version of [CSAwesome Topic 4.1](https://runestone.academy/ns/books/published/csawesome2/topic-4-1-data-ethics.html) 

---

# Ethical and Social Issues Around Data Collection

## Data Privacy

Your phone keeps a lot of information about you, including where you have been, what you buy, what games you play, etc. Here’s a [video](https://www.youtube.com/watch?v=bqWuioPHhz0) about the massive amounts of data our smartphones and computers collect about us.

If you have used your phone to give you directions to go somewhere, it probably tracks your location. Follow the directions in [this article](https://www.lifewire.com/location-history-google-maps-iphone-1683392) to see if you have location history settings on. You can also turn off location tracking, but it is useful when you want directions and it’s free.

**Reflection:** Do the benefits of apps that provide driving directions outweigh the lack of privacy for you? In what situations would it be beneficial or harmful for the app to track your location?

![Google Timeline Screenshot](Figures/googletimeline.png)

As users, we often don’t realize how much personal data we are giving away. If you use a computer or phone, your personal privacy is at risk.

As computer programmers, we must be aware of the risks to data privacy when our code collects and stores personal data on computer systems. Programmers should attempt to safeguard the personal privacy of the user. Legally and ethically, we must ask the users for permission to access and store their data. If there are data breaches where the data is stolen, we must inform the affected users. The laws are slowly catching up to our technology, and many countries and states are passing laws to protect data privacy.

Computer use and programs have beneficial and/or harmful impacts on personal security. Software apps for maps and driving directions are very useful, but they have impacts on personal security and privacy if they keep track of your location. This information could be beneficial, for example if you are lost and need to be found, but could be harmful and unsafe if someone unauthorized gains access to your location.

### Activity 1

<div class="task" markdown="block">

1. Explore a popular app or website and its data-collecting practices.
2. Explain the risks to privacy from collecting and storing personal data on computer systems.
3. Discuss the ethical and legal problems that may arise and how programmers can try to avoid them.
4. (Optional) Work in pairs or groups.

</div>

**More Resources on Data Privacy:**
- [1 minute video](https://www.cnbc.com/video/2018/03/23/everything-you-need-to-know-about-the-cambridge-analytica-scandal.html) about the Facebook Cambridge Analytica incident  
- [1 hour PBS special](https://www.pbs.org/wgbh/frontline/film/facebook-dilemma/#video-2) on Facebook  
- [What is Geo-fencing? (2 mins)](https://www.youtube.com/watch?v=gXiEBcb0Vs8)  
- [European General Data Protection Regulation (GDPR) (3 mins)](https://www.youtube.com/watch?v=j6wwBqfSk-o)

---

## Data and Bias

The fields of **AI (Artificial Intelligence)** and **Machine Learning (ML)** are rapidly growing and increasingly involve ethical questions about data collection, privacy, and resource use. Machine learning algorithms to create software like ChatGPT require massive amounts of data to learn from as well as massive amounts of energy use.

But where does this data come from? Often the data is collected from the internet, and the internet is full of biases. For example, if you search for professions like "programmer", "doctor", "CEO" in [Google Images](https://images.google.com/), you will probably see mostly images of white men. This reflects a bias in our world that AIs may learn. An AI could then generate text or images that are biased against historically underrepresented groups.

For example, in 2014, a prominent tech company started building an automated hiring tool — a resume-filtering AI trained on their current employees’ resumes — and ended up with an AI system that was biased against women ([ACLU article](https://www.aclu.org/news/womens-rights/why-amazons-automated-hiring-tool-discriminated-against)). This is a problem because the AI is learning from biased data and then creating biased outcomes that could affect people’s lives.

**Algorithmic bias** describes systemic and repeated errors in a program that create unfair outcomes for a specific group of users.

Bias in data can lead to unfair and unethical outcomes. For instance, facial recognition software has been shown to have higher error rates for people with darker skin tones. This is because the data used to train these algorithms often contains fewer examples of people with darker skin tones. As a result, the software is less accurate for these individuals, which can lead to discriminatory practices.

Watch [Gender Shades](https://www.youtube.com/watch?v=TWWsW1w-BVo) by computer scientist [Joy Buolamwini](https://www.poetofcode.com/) (MIT Media Lab and Algorithmic Justice League).

<iframe width="700" height="400" src="https://www.youtube.com/embed/TWWsW1w-BVo" frameborder="0" allowfullscreen></iframe>

### Activity 2

<div class="task" markdown="block">

1. Explain the importance of recognizing data quality and potential issues such as data bias when using a dataset in AI/ML applications.
2. (Optional) Work in pairs or groups.

</div>

**More Resources on Bias in Algorithms:**
- [AI, Ain’t I a Woman?](https://www.youtube.com/watch?v=QxuyfWoVV98), a poem by Joy Buolamwini  
- [Bias in Facial Recognition (TED Talk)](https://www.youtube.com/watch?v=UG_X_7g63rY) by Joy Buolamwini  
- [Report on police crime prediction software and bias](https://www.youtube.com/watch?v=7lpCWxlRFAw)

---

Programmers should be aware of the dataset collection method and the potential for bias before using the data to extrapolate new information or draw conclusions. Some datasets are incomplete or contain inaccurate data. Using such data can cause the program to work incorrectly or inefficiently. Or the dataset might be related to a specific question or topic and not be appropriate for answering different questions.

It is important for programmers and data scientists to take steps to mitigate bias in data collection and use. This can include using diverse and representative datasets, regularly testing algorithms for bias, and being transparent about the limitations of the software.

**Steps to Address Bias in Machine Learning:**
- Use diverse and representative datasets to train algorithms.
- Regularly test algorithms for bias and accuracy.
- Be transparent about limitations and potential biases.
- Involve diverse teams in development and testing.
- Implement ethical guidelines and standards for AI/ML use.

### Activity 3

<div class="task" markdown="block">

1. Go to [Google Dataset Search](https://datasetsearch.research.google.com/) and search for a dataset for "face recognition" or another topic of interest.
2. Find an appropriate (“good”) dataset and an inappropriate (“bad”) dataset for your topic.
3. Link to both datasets.
4. Explain why the datasets are appropriate or inappropriate (too small, incomplete, biased, etc.).
5. Explain how dataset choice could affect program results.
6. (Optional) Work in pairs or groups.

</div>

---

## Summary

- **(AP 4.1.A.1)** When using a computer, personal privacy is at risk. Programmers should attempt to safeguard the personal privacy of the user.
- Computer use and programs have an impact on personal security and data privacy. These impacts can be beneficial and/or harmful.
- **(AP 4.1.B.1)** Algorithmic bias describes systemic and repeated errors in a program that create unfair outcomes for a specific group of users.
- **(AP 4.1.B.2)** Programmers should be aware of dataset collection methods and potential for bias before drawing conclusions.
- **(AP 4.1.B.3)** Incomplete or inaccurate datasets can cause programs to work incorrectly or inefficiently.
- **(AP 4.1.C.1)** The contents of a dataset might be specific to one topic and not appropriate for other uses.


---

#### Acknowledgement
{: .no_toc }

Content on this page is adapted from [Runestone Academy - Barb Ericson, Beryl Hoffman, Peter Seibel](https://runestone.academy/ns/books/published/csawesome2/csawesome2.html).
{: .fs-2 }
