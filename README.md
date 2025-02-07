THE Questions that was eing tackeled here and the project descriptuon for the data used is as follows:
Data
A randomized clinical trial was conducted to test the efficacy of a new drug on the prevention of malaria for people travelling (visiting) to regions with high malaria transmission. The study took place in a remote village in Mozambique, in which adult visitors planning to stay for at least two months were asked to participate in the trial. The participants were enrolled within 24 hours of arrival, and randomly assigned to the receive the study drug or placebo (fake drug).

The inclusion (eligibility) criteria:

Having 18 or more years of age
Not having malaria infection (confirmed by negative PCR test)
No being pregnant
The trial was blinded, i.e., participant did not know if they were taking the active drug or placebo. The trial was blinded, i.e., participant did not know if they were taking the active drug or placebo. Data were collect at two time points, at enrolment and at end of follow-up period of 2 months.

The data collected at enrolment are provided in the file recruitment_data.csv and contains the following variables:

subject_id: the unique participant identifier assigned at enrolment
date_enrol: the date of participant enrolment, format: YYYY-MM-DD
date_birth: participant’s birth date, format: YYYY-MM-DD
sex: participant’s sex, coded 1 (Female) and 2 (Male)
weight_kg: participant’s weight in kilograms
height_cm: participate height in centimetres
malaria_origin: malaria transmission at the place of participant’s origin, coded 0 (no transmission), 1 (low transmission), 2 (moderate transmission), and 3 (high transmission)
treatment: the treatment group assigned to the participant, coded 0 (placebo) and 1 (active drug)
The data collected at the end of follow-up is in the end_data.csv, with the following variables:

subject_id: the unique participant identifier assigned at enrolment
date_end: date of the end of follow-up visit, format: YYYY-MM-DD
malaria_epi: total number of malaria episodes the participant had from the enrolment till end of follow-up
bednet: use of bed net by the participant during the study period, coded 0 (never), 1(sometimes) and 2 (always)
The data files are located in the data/orig subfolder.

The two data files where pre-processed in R to create a single final dataset for analysis, and saved to the file merged_data.rds in the data/proc subfolder.` During the pre-processing, new variables were created, namely:

age_y: age in years at enrolment
height_m: height in metres at enrolment
bmi: body mass index at enrolment
had_malaria: whether a participant had malaria during the study follow-up period (Yes/No)
The body mass index (BMI) is a measure of body fat based on height and weight, and is calculated as
BMI=wh2
where w
 is weight in kilograms and h
 is height in metres.

Exercises
Exercise 1
Import the final (merged) dataset into your R session, assigning to an R object named mds. Then print the structure of the mds data frame.

Are the variables data types in line with their description above?

Exercise 2 Solution:
# Write your code inside this code chunk
Exercise 2
One thing that can affect or distort the comparison of the two treatment groups (placebo vs active drug) with regard to the outcome of interest (having malaria during the study follow-up period) is the imbalance of the participant characteristics between the two treatment groups. Construct a table containing summary statistics of participant characteristics by treatment group. The characteristics to consider are: sex, body mass index, malaria transmission at the place of origin, age, and use of bed net. Include also the p-values from the appropriate statistical tests to check whether there are significant differences (of participant characteristics) between the two groups.

Checking your output table, are there significant differences? If yes, in what characteristics?

Exercise 2 Solution:
# Write your code inside this code chunk
Exercise 3
We are interested in comparing, visually, the distribution of the body mass index between the two treatment groups. Use a box plot to achieve this goal.

What are your conclusions? Are there any outliers?

Exercise 3 Solution:
# Write your code inside this code chunk
Exercise 4
The main objective of the study was to evaluate the efficacy of the new drug (active drug) in preventing malaria infection. That is, we hypothesize that the new drug reduces the probability of getting malaria infection, compared to placebo. Some participant characteristics might be malaria risk factors (i.e., associated with malaria). It is, therefore, important to check for this associations before performing the confirmatory analysis.

Check for possible associations between the participant characteristics and the outcome (had_malaria). The characteristics to check are: sex, bmi, age, and bednet. Present in form of table, similar to that of the Exercise 2. Include also the p-values.

What insights are getting from your output?

Exercise 4 Solution:
# Write your code inside this code chunk
Exercise 5
Suppose that, for answering the main research question, we are going to used multivariate logistic regression, having the variable had_malaria as the dependent variable and the treatment as one of the independent variables. Looking at your output of Exercise 4, what other independent variable would you include in the model?

Exercise 5 Solution:
