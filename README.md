# HackerEarth-Pet-Adoption    
## Rank: 94

### A ML multi-class classification project to identify pet and breed category

This projects helps classifying the pet and breed category provided the following features:
1. pet_id:	Unique Pet Id
2. issue_date:	Date on which the pet was issued to the shelter
3. listing_date: Date when the pet arrived at the shelter
4. condition:	Condition of the pet
5. color_type:	Color of the pet
6. length(m):	Length of the pet (in meter)
7. height(cm):	Height of the pet (in centimeter)
8. X1,X2:	Anonymous columns
9. breed_category:	Breed category of the pet (target variable)
10. pet_category: Category of the pet (target variable)

## Evaluation Metric
s1:  weighted average f1_score for breed category
s2:  weighted average f1_score for pet category 
score = 100*(s1+s2)/2

## Project Structure
1. train.csv and test.csv files contain the training and testing data, respectively
2. PetAdoption.ipynb file gives the walkthrough over the complete project. 

## Approach

1. Converted issue date and listing date to datetime and found the difference between the dates

2. Used a OneHotEncoder on the color_type column since it contained categorical features

3. Converted length in m to cm by mutiplying the column by 100

4. Replaced all the length values of 0 by the mean of the length column

5. Replaced the NaN values in condition column by "3" and converted the column to int data type

6. Dropped "issue_date", "listing_date","color_type" column

7. Used Standard Scaler on X1, X2, length and height

8. Removed the colour_type feature "Black Tiger" and "Brown Tiger" from training data since it wasn't present in test data

9. Created a Heatmap to see the correlation amongst all the features

10. Finally used LGBM classifier to train the data and create the predictions


## Credits
This dataset was from HackerEarth competetion and hence credit for the dataset used for training goes to https://www.hackerearth.com/challenges/competitive/hackerearth-machine-learning-challenge-pet-adoption/problems/
