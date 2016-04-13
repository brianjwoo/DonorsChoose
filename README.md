# DonorsChoose
Predictive Modeling using the data provided by DonorsChoose

This repo contains some basic EDA and modeling based on the data provided by DonorsChoose, an organization that provides infrastructure allowing school teachers to fund projects using crowd sourcing from donors all over the world. 

The data, which consists of a number of tables, was obtained from:
http://data.donorschoose.org

Within the tables are basic information about projects, the resources requested in each of the projects and the various donors as well as their contribution amount.

![Donors Choose Schema]
(https://raw.githubusercontent.com/brianjwoo/DonorsChoose/master/images/DC_schema.png)

##Objective:
The purpose of this project is to gain insight that would hopefully allow future teachers to structure their proposal in a manner that would help them get funded. Future exploration of the data will allow us to better understand the general audience of the site, the donors, whose generosity makes these projects possible.

Based on our EDA, we notice a couple of things. First, the funding rate has remained relatively consistent at approximately 80%, despite the fact that significantly more projects are being submitted year over year. We can observe that unsuprisingly projects with lower cost are funded more frequently and that those which ultimately get funded have an average of 6 donors compared to 2 for projects that ultimately expire. 

![EDA plots]
(https://raw.githubusercontent.com/brianjwoo/DonorsChoose/master/images/project_per_day.png)
Here we show a quick overview of the projects that are submitted are either completed or expire. Interestingly, there are some very large peaks seemly random peaks in the data. Further investigation of them shows that there are certain times where the organization gets a lot of publicity, which also increases the number of projects funded after that duration.  

As an example:
http://blogs.edweek.org/teachers/teaching_now/2015/05/stephen-colbert-funding-for-donors-choose-project.html

![EDA plots2]
(https://raw.githubusercontent.com/brianjwoo/DonorsChoose/master/images/project_categories.png)
Another plot of interest is the categories created by DonorsChoose. Unsuprisingly, the bulk of the projects focus on Literacy, Literature & Writing, and Mathematics, as many of the schools represented are from less affluent areas. Later on, when we examine cluster the items requested, we will see that many of them fall into clusters, specifically around books. 

##Results:
For our classification, we choose to compare 2 different models, a sklearn's RandomForest Classifier and xgBoost(Gradient Boosted Trees). We can effectively evaluate our model using a ROC curve.

![ROC Curve]
(https://raw.githubusercontent.com/brianjwoo/DonorsChoose/master/images/roc_curve.png)

In addition to showing feature importance, our RFC is also able to determine what features are important for our model. The model utilizes the Day feature, which represents the time since the first project was submitted. The variable Month is also present, as we can show in our EDA that months later in the year tend to have slightly more projects funded (2-4%) compared to earlier in the year. The numbers are all dummy variables representing the features generated by our clustering model. The other two feature LandSQMI, pctRenterOcc, and MedianHValue are features added to replace the original ZIP code feature.

 
###Feature Importances using RFC
###=====================================
1. Day
2. payment_processing_charges
3. total_price_including_optional_support
4. total_price_excluding_optional_support
5. 3
6. 2
7. 4
8. 1
9. students_reached
10. LandSQMI
11. Month
12. pctRenterOcc
13. MedianHValue



###Groups Based on Text Clustering

Group: 0

illustrator nancy john robert david jane james michael translator brian kevin peter tomie mary
chris editor jack robin barbara steven pat harrison ann susan smith martin henkes van paul laura 

Group: 1

level extra nonfiction library book set kgr fiction readers guided reading sightword lexile reader combo rigby
right beginning recovery libra platinum fictionnonfiction parent word libraries just plus levels blue sightwords 

Group: 2

set complete library boxed classroom readalongs favorite collection rex paperback leveled write student wipe play
giant ball box board piece classic lego jumbo puzzle magnetic class pieces fictionnonfiction games extra 

Group: 3

paper construction amp sulphite superbright green blue holiday red brown dark light pink white orange yellow
sheets taye tabu violet targ tabk tavt tapn sky tahg black tawt riverside tard 

Group: 4

series stine goosebumps john vol high jeff nancy rick bluford diary clues riordan street secrets anne smith time
classic boxed horrorland matt kinney publishing darren shan krulik kimani tru mysteries 

Group: 5

ipad apple mini case wifi tablet retina ios display cover generation air stand smart mdlla space griffin screen white
protective gray ipod survivor proof new feature technology silver blue protection 

