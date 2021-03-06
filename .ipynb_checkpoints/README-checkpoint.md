# EthiCars
## The Social Dilemma of Autonomous Vehicles

### Description
Autonomous vehicles should make transportation safer but there will be unavoidable accidents happening due to technical failure or unexpected events. What choice should the AI algorithm make from two horrible outcomes? Should it sacrifice the passengers by avoiding hitting someone on the road, or should it hit a dog or a doctor walking on the pedestrian crossing? These and similar scenarios are the subjects of MIT’s “Moral Machine” project that collects humans’ choices in an online survey to help the development of “ethical” AI decision making.

I'm going to analyze the responses to various scenarios and try to understand and visualize how this information could influence decision making of a machine learning algorithm.

### Sources
Moral Machine project https://www.moralmachine.net/

The social dilemma of autonomous vehicles https://www.media.mit.edu/publications/the-social-dilemma-of-autonomous-vehicles/

Moral Machine dataset on OSF https://osf.io/3hvt2/?view_only=4bb49492edee4a8eb1758552a362a2cf


* imported the csv file to a Spark DF and created a schema to cast numbers to integer type

* SharedResponses.csv had 70,332,355 rows and 41 columns
    * this includes single scenario selections
    
* SharedResponsesSurvey.csv had 11,286,141 rows and 27 columns
    * this includes survey participants' demographic information and their choices
    
* converted 100,000 rows to a Pandas DF from both datasets for EDA

* Transposed the DFs to better understand all the columns

* Checked the # of responses by country and surprisingly Hungary had a pretty good representation given its size

* created a Spark SQL query to merge SharedResponses and SharedResponsesSurvey datasets for a subset of responses from Hungary only ordered by user ID, response ID and scenario to gain a better understanding of how those two tables relate to each other (this almost put my laptop on fire, but it should give me a more managable size of DF to do EDA on)



