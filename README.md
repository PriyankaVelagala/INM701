# INM701 : Predicting Data Science and STEM Salaries
## Joel Davis, Priyanka Velagala

# Overview 
For our analysis of artificial intelligence techniques, we have selected a dataset composed of
user-entered salary data from www.levels.fyi, a site for those employed in STEM industries to
share compensation data. For each salary reported, users also report information such as age,
gender, level of education, position, company and among other relevant factors.

# Objectives 
Our objective is to build a regression model that can predict the total compensation of a user
based on available data such as education level, job title, years of experience and more. Our
motivation is that this model will allow those seeking employment in STEM industries to target
locations, job titles or specific ‘tags’ in job postings to maximise their total compensation, and
show the impacts of their current experience on future earnings. Based on the accuracy from
the model, we hope to make available to job seekers a baseline/approximate figure they can
use to make the negotiation process more transparent.

# Findings
Overall, our model achieved low accuracy however several machine learning and
artificial intelligence techniques were used to investigate the impacts of a variety of features on our output,
total yearly compensation for employees in STEM and data science.

I believe something upon which we could have improved was our data cleaning and exploration.
We decided to eliminate several features from our modelling due to time constraints or
complexity - ‘Location’, for example - but on reflection, I believe the additional work could have
resulted in a significant improvement in the accuracy of our models. In the case in point
(location), It stands to reason that there is a correlation between where you work and how much
you earn, and using the site’s own rudimentary statistical analysis features, the median salary of
a software engineer in New York is $180,000 , whereas the median value of the same role is
$43,000 in India. This correlation would imply some improvements to our model could have
been made by inclusion of this feature.

Furthermore, inclusion of the ‘Company’ feature could have yielded some useful results - our
aim was to gain insight in compensation for roles across the STEM and data science industry,
and though this column contains >1,500 unique values for 62,000 rows (and so we believed the
data to only be of sufficient quality for a handful of companies), those companies with large
numbers of reported data points could have been useful in making predictions. For example, the
so-called “FAANG” group of companies composed of Facebook, Amazon, Apple, Netflix and
Google make up almost 25% of our data points and it is reasonable to assume that these
companies have higher average pay than other companies in the industry. Therefore, we could
have created a new variable (a.k.a feature engineering) to indicate whether the row was FAANG
or non-FAANG, further completing our data set.

A second point of reflection was that of our imputation of values in ‘Education’. After completing
our model, it occurred to us that using such a large number of imputed values (>50%) could
negatively impact our performance. So, in comparison, we ran our models again on a smaller
dataset composed of solely user-entered values for education, dropping all other rows. This can
be found in the ‘PredictTotalCompensation-UsingTrueEduValue-entireDS.ipynb’ notebook, in the
GitHub repository. The results of this experiment were lower 𝑅 values and higher RMSE, 2
possibly indicating either that our imputation was not largely impactful on our results, or that the
dataset was reduced too far, and the approximately 20,000 remaining rows do not provide
enough data to successfully implement a machine learning model.

Investigation too could have been made into the impacts of specific features on total
compensation - race and gender to be precise. This would be an interesting piece of future work
to undertake, as we believe that there could be some discoveries to be made from this data that
could help improve equal pay conditions in the industry.
