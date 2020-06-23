# Capstone-Project---Hand-Posture-Recognition-
A Predictive and Descriptive Machine Learning Model for analyzing sensor data to classify Hand Postures

Information on the Project:

•	A Vicon movement catch camera framework was utilized to record 12 users performing 5 hand stances with
markers joined to one side glove. 

•	A total of 12 sensors set on the glove were used to collect data.

•	Every instance has a minimum set of 3 markers’ data to be utilized as framework for the hand, and 
additional 9 different markers which can be included or occluded. 

•	3 markers were joined to the thumb with one over the thumbnail and the other two on the knuckles. 
2 markers were connected to each finger with one over the fingernail and the other on the joint between the proximal and center phalanx. 

•	Likewise, because of self-impediment because of the direction and setup of the hand and fingers, numerous 
records have missing markers. Incidental markers were likewise conceivable because of ancient rarities in the
Vicon programming's marker recreation/recording process and different articles in the catch volume. Thus, the
quantity of noticeable markers in a record changed extensively. 

•	At last, any record that contained less than 3 markers was evacuated. The prepared information has all things 
considered 12 markers for each record and in any event 3. 

•	Because of the way where information was caught, all things considered, for a given record and client there 
exists a close to copy record beginning from a similar client. We prescribe in this manner to assess grouping 
calculations on a forget about one-client premise wherein every client is iteratively forgotten about from 
preparing and utilized as a test set. One at that point tests the speculation of the calculation to new clients.
A User ascribe is given to suit this system. 

•	This dataset might be utilized for an assortment of assignments, most clear of which is pose acknowledgment 
by means of characterization. One may likewise endeavor client ID. On the other hand, one may perform grouping 
(compelled or unconstrained) to find marker disseminations either as an endeavor to foresee marker personalities
or acquire measurable depictions/perceptions of the stances. 

•	Abstract: 5 types of hand postures from 12 users were recorded using unlabeled markers on fingers of a glove 
in a motion capture environment. Due to resolution and occlusion, missing values are common.

- Data Characteristics: Multivariate	
- Number of Instances:	78095
- Attribute    Characteristics:	     
- Real	Number of Attributes:	38
- Associated Tasks:	Classification, Clustering	
- Missing Values?	Yes

Class ranges from 1 to 5 with:
1=Fist (with thumb out)
2=Stop (hand flat)
3=Point1 (point with pointer finger)    
4=Point2 (point with pointer and middle fingers) 
5=Grab (fingers curled as if to grab)


Procedure and EDA:
1)	First, we loaded the dataset called Posture.csv. The dataset contains total 38 
numerical variables with total 78096 observations.
2)	Here the variables are the coordinates of the hand motion and as per the motion 
the coordinates are marked. Our target variable is Class.
3)	There are total 974700(32.8%) missing cells in the data.
4)	The dataset is highly cardinal. There is no presence of categorical data.
5)	For ex: The variable X3 contains 0.9% missing value i.e. 690 missing values
6)	So, we firstly changed our data type of class variable to int data type 
7)	We dropped all the features containing more than 50% of missing data i.e. from X7 to Z11 
8)	After that we changed the remaining features data type into float data type
9)	We dropped class 0 as it was mentioned in the problem statement to ignore 
10)	We then checked whether all the missing values in the form of (‘?’) are changed into nan values
11)	After successfully changing the values into null values we then moved ahead with the single 
imputation method which actually was not appropriate approach so we later on we decided 
to go for multiple imputation method 
12)	We moved ahead with one of the multiple imputation methods which is called MICE
13)	We had to change to our approach to our problem because we had some computational 
errors when we used MICE method for imputation. So due to limited resources, we look 
at other imputation methods.
14)	Later we decided to go with fast KNN imputation which led to successful execution. 


Classification Report: -

        Class          precision      recall     f1-score      support

         1               0.99           0.99       0.99          4869
         2               0.91           0.94       0.93          4619
         3               0.96           0.96       0.96          4826
         4               0.94           0.92       0.93          4373
         5               0.95           0.95       0.95          4742

    accuracy                                       0.95          23429
    macro avg            0.95           0.95       0.95          23429
    weighted avg         0.95           0.95       0.95          23429


