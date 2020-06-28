# **Hacker Stats in Python**<br/>by **Justin Bois**


## Step 1: Foundations 


### A. What problem(s) will students learn how to solve? (minimum of 5 problems)

This live training will review the concepts of statistical inference laid out in Statistical Thinking in Python I and II using a new data set (one that I think is rather fun!). The goal is to reinforce the concepts and techniques from those courses and help students gain confidence applying them to new data analysis tasks. Specifically, we will:

- Review fundamental notions of probability.
- Perform graphical exploratory data analysis (EDA).
- Review concepts of confidence intervals and null hypothesis significance tests (NHSTs).
- Apply bootstrap methods for computing confidence intervals.
- Investigate correlations in two-dimensional data.
- Perform an NHST comparing two treatments in a data set.


### B. What technologies, packages, or functions will students use? Please be exhaustive.

- NumPy
- pandas
- seaborn
- Jupyter notebooks using Google Colab
- [dc_stat_think](https://github.com/justinbois/dc_stat_think)


### C. What terms or jargon will you define?

In our probably review, we will define and discuss:

- **Frequentist interpretation of probability**: The probability of an observation represents a long-run frequency over a large number of identical repetitions of an experiment. These repetitions can be, and often are, hypothetical. For example, if I were to list an item on ebay, the probability that it will sell for over $100 is the fraction of times it do so in a very large number of hypothetical worlds in which I sell the item on ebay.
- Probability distributions: Probability distributions provide the link between events to probability. For example a Normal distribution might link people's heights to probability. It is highly probable that a person is between five and six feet tall, but improbably that a person is above seven feet tall.
- Generative distributions: Obtaining a measurement (by any means, experimentation, surveys, consumer trials, etc.) involves drawing samples out of a probability distribution. This distribution is called a generative distribution, and we do not in general know what it is. We can make models for the generative distributions, and we do this kind of model in the Statistical Thinking Courses, but we will not cover that in this live session.
- Empirical distributions: An empirical distribution can be defined simply in terms of measured data. When we draw samples out of an empirical distribution, we simply randomly choose measurements we already made.
- The plug-in principle: Under the plug-in principle, we use the empirical distribution in the place of the (unknown) true generative distribution in all of our statistical inference. This is the approach we will take in this live session.



### D. What mistakes or misconceptions do you expect? 

- The most common misconception is often about what constitutes a null hypothesis significance test. The result of a NHST is a p-value, defined as follows. Assume null hypothesis is indeed true. With this assumption in place, the p-value is the probability of obtaining a value of a test statistic at least as what was observed. So, to specify a null hypothesis, we need a clear definition of the null hypothesis, the test statistic, and what it means to be at least as extreme as.
- The distinction between a bootstrap hypothesis test and a permutation test is often confusing. Different hypotheses may be assessed by the two approaches. A permutation hypothesis can address the null hypothesis that two data sets of data come from the same generative distribution. A bootstrap hypothesis test can address a null hypothesis, e.g., that two data sets come from two different generative distributions, but they have the same mean.
- The definition of a confidence interval is sometimes a sticking point. A 95% confidence interval of a mean (or median, standard deviation, ...) may be defined as follows. If we were to do a measurement again and again and again, then the mean (or median, standard deviation, ...) that we compute from the data will fall within a 95% confidence interval for 95% for these repeated experiments. In practice, we repeat the experiment by sampling out of the empirical distribution; this is bootstrapping.


### E. What datasets will you use? 

We will be working with a fun data set. In a 2016 paper, [Beattie, et al.](https://doi.org/10.1098/rsos.160321) used the [Glasgow Facial Matching Test](https://en.wikipedia.org/wiki/Glasgow_Face_Matching_Test) (GFMT, [original paper](https://doi.org/10.3758/BRM.42.1.286)) to investigate how sleep deprivation affects a human subject’s ability to match faces, as well as the confidence the subject has in those matches. Briefly, the test works by having subjects look at a pair of faces. Two such pairs are shown below.

![GFMT faces](assets/gfmt_faces.png)

For each pair of faces, the subject gets as much time as he or she needs and then says whether or not they are the same person. The subject then rates his or her confidence in the choice.

In this study, subjects also took surveys to determine properties about their sleep. The Sleep Condition Indicator (SCI) is a measure of insomnia disorder over the past month (scores of 16 and below indicate insomnia). The Pittsburgh Sleep Quality Index (PSQI) quantifies how well a subject sleeps in terms of interruptions, latency, etc. A higher score indicates poorer sleep. The Epworth Sleepiness Scale (ESS) assesses daytime drowsiness.

We will explore how sleep disorders affect subject's ability to discern faces and their confidence in doing so.


## Step 2: Who is this session for?

This session is for anyone who wants to sharpen their skills in statistical inference. These skills apply across all industries and disciplines of interest to DataCamp learner; they are key for anyone working with data. Participants should have completed DataCamp courses Statistical Thinking in Python I and II.


### What roles would this live training be suitable for?

*Check all that apply.*

- [x] Data Consumer
- [x] Leader 
- [x] Data Analyst
- [x] Citizen Data Scientist
- [x] Data Scientist
- [x] Data Engineer
- [ ] Database Administrator
- [x] Statistician
- [x] Machine Learning Scientist
- [ ] Programmer
- [ ] Other (please describe)

### What industries would this apply to?

The topics of this live training are really general. Performing EDA, computing confidence intervals, and (though to a lesser extent) performing hypothesis tests apply across so many industries and applications. Whether are you doing business analytics, quality control, public health, science, really anything involving collection and interpretation of data, statistical inference plays an important role.


### What level of expertise should learners have before beginning the live training?

Learners should be able to do the following heading into the live session.

- Extract columns from pandas DataFrames.
- Be comfortable with NumPy, particularly the random module.
- Be able to make basic plots with Matplotlib; simple scatter plots should be sufficient.
- We will review computing summary statistics (like means and medians), drawing bootstrap samples, and performing linear regressions, but familiarity with those methods will be helpful.


## Step 3: Prerequisites

Learners should have completed DataCamp courses Statistical Thinking I and II. 


## Step 4: Session Outline

### Introduction Slides 
- Introduction to the webinar and instructor (led by DataCamp TA)
- Our approach to statistical inference
  + Statistical inference: quantification of uncertainty
  + The frequentist interpretation of probability and probability distributions
  + Hacker stats allows direct application of probability without mathematical gymnastics
- Objectives
  + Obtain plug-in estimates and confidence intervals for pertinent parameters
  + Compare effect sizes between two samples
  + Perform a null hypothesis significance text
  + ...all with hacker stats using Python!
- Introduction to the data set
  + Domain knowledge is key for determining analysis procedures (no data scientist should work alone)
  + Introduction to GFMT and sleep disorder study


### Live Training

#### Exploratory data analysis
- Import data into a pandas DataFrame and display using `df.head()`.
- Add a column to a data frame.
- Extract a column while dropping NaNs.
- Generate ECDFs.
- Make scatter plots of possibly correlated variables.

#### Bootstrap confidence intervals
- Review of bootstrapping procedure, definition of a confidence interval, and the plug-in principle.
- Write a function to obtain bootstrap samples.
- Compare an ECDF of a bootstrap sample to the original data set.
- Write a function to obtain bootstrap replicates.
- Make an ECDF of bootstrap replicates.
- Compute percentiles of bootstrap replicates to obtain a confidence interval.
- Make a graphical display of confidence intervals.
- **Q & A**

#### Pairs bootstrap confidence intervals
- Write a function to obtain pairs bootstrap samples.
- Write a function to obtain pairs bootstrap replicates of the Pearson correlation.
- Compute percentiles of bootstrap replicates to obtain a confidence interval.
- For what aspects of this data set should we perform a linear regression?
- Bonus assignment for after the live session: Perform a linear regression where appropriate and give a pairs bootstrap confidence interval for the slope.

#### Null Hypothesis significance testing: a permutation test
- Review definition of p-value and essential pieces of NHST specification.
- Hacker stats approach: *simulate* data generation under the null hypothesis.
- Hypothesis: two variables are identically distributed. Generate permutations to simulate it.
- Compute p-value from permutation samples.
- Bonus assignment for after the live session: How would you simulate a null hypothesis that the two variables are not necessarily identically distributed but do have the same mean? Simulate this and compute a p-value.


### Ending slides
- Recap of what we learned
- Emphasize the importance of thinking probabilistically.
- You can use your computer to do probability directly.

<!-- ## Authoring your session

To get yourself started with setting up your live session, follow the steps below:

1. Download and install the "Open in Colabs" extension from [here](https://chrome.google.com/webstore/detail/open-in-colab/iogfkhleblhcpcekbiedikdehleodpjo?hl=en). This will let you take any jupyter notebook you see in a GitHub repository and open it as a **temporary** Colabs link.
2. Upload your dataset(s) to the `data` folder.
3. Upload your images, gifs, or any other assets you want to use in the notebook in the `assets` folder.
4. Check out the notebooks templates in the `notebooks` folder, and keep the template you want for your session while deleting all remaining ones.

You can author and save your progress on your notebook using **either** of these methods.

_**How to author your notebook: By directly saving into GitHub**_

1. Preview your desired notebook, press on "Open in Colabs" extension - and start developing your content in colabs _(which will act as the solution code to the session)_.  :warning: **Important** :warning: Your progress will **not** be saved on Google Colabs since it's a temporary link. To save your progress, make sure to press on `File`, `Save a copy in GitHub` and follow remaining prompts.
2. Once your notebooks is ready to go, give it the name `session_name_solution.ipynb` create an empty version of the Notebook to be filled out by you and learners during the session, end the file name with `session_name.ipynb`. 
3. Create Colabs links for both sessions and save them in notebooks :tada: 

_**How to author your notebook: By uploading notebook into GitHub**_

1. Preview your desired notebook, press on "Open in Colabs" extension - and start developing your content in colabs _(which will act as the solution code to the session)_.  Once you're done, press on `file` - `download .ipynb` file - and overwrite the notebook by uploading it into GitHub. 
2. Once your notebooks is ready to go, give it the name `session_name_solution.ipynb` create an empty version of the Notebook to be filled out by you and learners during the session, end the file name with `session_name.ipynb`. 
3. Create Colabs links for both sessions and save them in notebooks :tada: 


You can check out either of those methods in action using this [recording](https://www.loom.com/share/1eeb148129244edd93fbc34bf5dc7f0d).
 -->