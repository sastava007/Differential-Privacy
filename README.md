
# Differential Privacy
Differential Privacy is one of the most innovative methods of cyber security that works with aggregated user data to extract the information while keeping the data of individual users entirely private by introducing randomness into the process of data retrieval.

> *“Differential privacy” describes a promise, made by a data holder, or curator, to a data subject: “You will not be affected, adversely or otherwise, by allowing your data to be used in any study or analysis, no matter what other studies, data sets, or information sources, are available.”*

## Need of DP
Let's consider a simple use case where we’re curating (or managing) a sensitive database and would like to release some statistics from this data to the public. However, we have to ensure that it’s impossible for an adversary to reverse-engineer the sensitive data from what we’ve released given enough computation power and time.

The problem of statistical disclosure control revealing accurate statistics about a population while preserving the privacy of individuals has a venerable history. Netflix​ in 2006, announced a [challenge](https://www.diva-portal.org/smash/get/diva2:1113852/FULLTEXT01.pdf) for improving their recommendation algorithm by releasing 100 million anonymized movie ratings. Although the data sets were constructed to preserve customer privacy, still two researchers from the UT Texas, Austin were able to identify individual users by matching the data sets with film ratings on the IMDb.

<p align="center">
<img src="https://miro.medium.com/max/400/1*IVd-Xygy7BgYqubqoQcWBg.gif" height="340px" width="500px">
</p>


## Case Study
## 1. An analysis of Mental Health in Tech Survey with/ without preserving Data Privacy
The purpose of this demo is to showcase the utility of ​[OpenDP](http://opendp.io/)​ differential privacy framework by making statistical queries to data with and without privacy-preserving mechanisms. As we compare query results side-by-side, we show that conclusions about the data are similar in both settings: without a privacy-preserving mechanism, and with differential privacy mechanism.
		
**Data Set & Overview of each Attribute** 

The mental health in tech survey data set is released by ​ OSMI​ which consists of 27 questions, answered by 1,259 volunteers. The data used in the analysis were preprocessed i.e the original age, gender, and country variables were mapped into categories for the analysis.

● `Age`​ : 21-30yo (0), 31-40yo (1), 41-50yo (2), 51-60yo (3), 60yo+ (4).

● `Gender`​ : Male/Man (1), Female/Woman(2), all other inputs (0).

● `Country`​ : United States (1), United Kingdom (2), Canada (3), other countries (0).

● `remote_work`​ : Binary value that indicates if participant works remotely more than 50% of the time.

● `family_history`​ : Binary value that indicates if the participant has a family history of mental illness.

● `Treatment` : Binary value that indicates if the participant have sought treatment for mental illness.

Now, we will make statistical queries on different variables to generate a comparative analysis of results obtained from data with/ without differential privacy mechanisms.

1. **Age**

		The true age distribution is: ​ [478, 554, 149, 26, 6]
		The age histogram obtained using DP is: ​ [458 555 148 48 25]
    
<p align="center">
<img src="https://lh4.googleusercontent.com/YNN8vspzz-qkdUybVqZKrXesJvQTRrMdJ3Hj_ryRZ3HY-imGAK3SsWeBAprdE0SXWqrfS5N0ToQHt6in6zKgKcc4uIVsouRM-1vARBlNvl1ZA62dviyjqpdAr3737UN9" height="450px" width="680px"></img>
</p>

2. **Country**

		The true country distribution is: ​ [240, 732, 175, 66]
		The country histogram obtained using DP is: ​ [257, 810, 186, 63]
		
<p align="center">
<img src="https://lh6.googleusercontent.com/T2lEuy04J0BHez7dPmb_6pdCgcu-n6_SHcrF_52Qb_XePn09dmclV3sh3pRVr4ifaRBL0_Kxi_FdZLbSjJKnrIeD_UNBeHWKzsPcr7U6DX4DcMrKHvhbGQn5QexzVZgc" height="450px" width="680px"></img>
</p>


3. **Gender**

		The true gender distribution is: ​ [16, 955, 242]
	    The gender histogram obtained using DP is: ​ [52, 990, 238]
        
<p align="center">
<img src="https://lh6.googleusercontent.com/QdC-dUeyfeUTBf7dApoSKBBaz92j_ZdPKan7V3pqwSzS4OQYhSiZTM3ER-qcl5Fsm3HdLORULgOyhHQDwsgefffapzBtioYPhwp2X0KLjMB5ArXbrAO2_JtC6x04P450" height="450px" width="680px"></img>
</p>

4. **Remote Work**

		The true remote work distribution is: ​ [360, 853]
		The remote work histogram obtained using DP is: ​ [355, 898]
 
<p align="center">
<img src="https://lh3.googleusercontent.com/hmYvcWyvr0Si8mheiEjZbefyGUsU59Qdf8uSTpnA9tfECI7GsRt7uysfn7NxVJ0WK0G0thHTsBqhWTnGHvUbdiIq1v7zJA736MCEdehrOG-89yAXLCVPbWUfGm7tOfTv" height="450px" width="680px"></img>
</p>

5. **Family History**

		The true count of participants with a family history of mental illness is: ​ [480, 733]
		The family history histogram obtained using DP is: ​ [517, 709]
		
<p align="center">
<img src="https://lh6.googleusercontent.com/SWSaV7bNqa-nYUj33NoB7TnOKtSWntLfy3DLCwrvVlxGGe_H-qMyaVzfVekoeMOnpUQV2xKhSXgHN93HvQHAbItEq_gF6xfzVqQvKCbRZ4xePH-QsQB9OYM3KAYrERcV" height="450px" width="680px"></img>
</p>	

6. **Treatment**

		The true count of participants diagnosed with mental illness is: ​ [619, 598]
		The mental illness obtained using DP is: ​ [604, 612]

<p align="center">
<img src="https://lh6.googleusercontent.com/xl06oSmwNlLJt-7EFka-gTSP550oA3F9pyjWcZfAuXC9IxwYbJck4UfpBVmCFHuFtrQc77yOOjXupsPmoWHPyg3lGlY1-XilK9xbcmyiFshkkTOvgb2wRr1B-8Fx9egC" height="450px" width="680px"></img>
</p>

## 2. Usefulness of Differential Privacy in handling the attack on an individual’s data

In this demo, we will examine perhaps the simplest possible attack on an individual's private data and what the differential privacy can do to mitigate it. We are considering a dataset of 10,000 people having attributes like (name, sex, age, education, income, married, race).

<p align="center">
<img src="https://lh3.googleusercontent.com/KKabUvzLKxDCpBd9VD8i92MHizNJNZ6ftGbi4TXP5OazM-klEMDYMuRkD2Ee4CHNrY15REgV1-IJnoBTl5HWmpFM_F_3cxtvsXWN1pb8xZmh7U5EIe5mNOXlhlXnFdYQ"></img>
</p>

Consider an attacker who knows everything about the data except for the person of interest's (POI) income, which is considered private. They can back out the individual's income very easily, just by asking for the mean overall mean income.

**`POI_income = overall_mean * n_obs ​ - ​ known_mean * known_obs`**

But if the attackers were made to interact with the data through differential privacy and was given a privacy budget of ​ `ε = 1`​ . Now, they should use tighter data bounds than they know are actually in the data in order to get a less noisy estimate and need to update their known_mean accordingly.

Upon executing the code in the attached Jupyter notebook the result I got are as follows:

    Known Mean Income: 26886.001600160016
    Observed Mean Income: 26883.930944271226
    Estimated POI Income: 6179.4427122677835
    True POI Income: 6000.0


**Note**: I've worked upon this project as a part of my junior year Information System Security coursework at the Indian Institute of Information Technology(IIIT), Gwalior in the supervision of Dr. Debanjan Sadhya.

[[Presentation Slides](https://docs.google.com/presentation/d/e/2PACX-1vQnh0iMepsSjnE6Jh43_5YvVubXHDRMMFUOe2mCBELfDuENJdCLV5LpLAJ6jiIgcQ/pub?start=false&loop=false&delayms=3000)]     [[Project Report](https://drive.google.com/file/d/1fFaAAPkrSPE4_mvH3cPdXa8SwEioSTmq/view?usp=sharing)]
