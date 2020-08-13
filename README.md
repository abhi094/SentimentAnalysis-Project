# Sentiment Analysis App 
This application has been developed as a project to implement end to end Machine Learning. Then goal is to train a sentiment analysis app using scraped data and predict the rating for a review. Then it can be deployed to EC2 and be used as as webservice. 

<img src="https://github.com/abhi094/SentimentAnalysis-Project/blob/master/.github_readme_assets/sentimentAnalysis_demo.gif">

### Phases of the project :
1. [Data Collection](https://github.com/abhi094/SentimentAnalysis-Project/blob/master/README.md#1-data-collection-)
2. [Data Cleaning](https://github.com/abhi094/SentimentAnalysis-Project/blob/master/README.md#2-data-cleaning-)
3. [Training with CNN](https://github.com/abhi094/SentimentAnalysis-Project/blob/master/README.md#3-training-with-cnn-)
4. [Building a Web-App]()
5. [Dockerizing the Application]()
6. [Deploying to AWS EC2]()
#### 1. Data Collection : 
The data is collected form [Trustpilot](https://www.trustpilot.com/). This website has a huge collection of reviews on different shops and companies. It also has a rating for each review which can be used to train the model. The scraped data is saved in two CSV files, one with links to all companies and the other with the actual rating and reviews. A total of 1.3GB of reviews was scrapped from the website. Scraping was done using Python [Selenium](https://selenium-python.readthedocs.io/) and [Scrapy](https://scrapy.org/).

<img src="https://github.com/abhi094/SentimentAnalysis-Project/blob/master/.github_readme_assets/trustpilot_capture.PNG" height="400" width="800">

[[Back to Phases of Project](https://github.com/abhi094/SentimentAnalysis-Project/blob/master/README.md#phases-of-the-project-)]

#### 2. Data Cleaning :
The data was loaded into a dataframe for basic cleaning and manupulation.

[[Back to Phases of Project](https://github.com/abhi094/SentimentAnalysis-Project/blob/master/README.md#phases-of-the-project-)]

#### 3. Training with CNN :
To use CNN in this case, [1D-Convolutions](https://towardsdatascience.com/understanding-1d-and-3d-convolution-neural-network-keras-9d8f76e29610) is used. The CNN will try to predict if a review is good, average or bad. The review data is feeded to the CNN and after 3 to 4 epochs ~70% accuracy is achieved for all three cases. (I did not go any further as I was training on my laptop with an i5-10210U)

<img src="https://github.com/abhi094/SentimentAnalysis-Project/blob/master/.github_readme_assets/Annotation%202020-07-30%20143806.png" height="300" width="500">

[[Back to Phases of Project](https://github.com/abhi094/SentimentAnalysis-Project/blob/master/README.md#phases-of-the-project-)]

#### 4. Building a Web-App :
The web app will predict the rating for a review of the [Fortune 500](https://fortune.com/fortune500/) companies. The web app will have four parts : 
1. DB ([Postgresql](https://www.postgresql.org/))
2. ML Model (Train from CNN)
3. API ([Flask](https://flask.palletsprojects.com/en/1.1.x/))
4. Front-end Client ([Dash](https://plotly.com/dash/))

<img src="https://github.com/abhi094/SentimentAnalysis-Project/blob/master/.github_readme_assets/webservice%20components%20.png" height="320" width="500">

[[Back to Phases of Project](https://github.com/abhi094/SentimentAnalysis-Project/blob/master/README.md#phases-of-the-project-)]

#### 5. Dockerizing the Application :
