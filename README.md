# DonorsChoose
Predictive Modeling using the data provided by DonorsChoose

This repo contains some basic EDA and modeling based on the data provided by DonorsChoose, an organization that provides infrastructure allowing school teachers to fund projects using crowd sourcing from donors all over the world. 

The data, which consists of a number of tables, was obtained from:
http://data.donorschoose.org

Within the tables are basic information about projects, the resources requested in each of the projects and the various donors as well as their contribution amount.

The purpose of this project is to gain insight that would hopefully allow future teachers to structure their proposal in a manner that would help them get funded. Future exploration of the data will allow us to better understand the general audience of the site, the donors, whose generosity makes these projects possible.

TO DO:
Explore churn rate of users that donate and try to determine users the probability that a given user will return.
Provide recommended projects based on their projects they have previously donated to. Either from a specific causes they prefer to donate to, or whether they prefer to donate to a specific school.


**The ROC Curve in Notebook #4 is most likely incorrect as it seems the model is overfit. This is probably because I regenerated a different split of the sample, which results in all cases being higher. The best is to train the model with more data using the same parameters and early stopping.
