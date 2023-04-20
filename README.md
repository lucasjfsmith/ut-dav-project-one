# ut-dav-project-one
Analyze fast food data from different popular restaraunts based on nutritional value.

### Team Members:
Luke Smith
Kim Reitema
Donna Das
Shahad Rahman


## Overview
To complete this project, we looked to answer a few different questions around key nutrients and nutritional values for various items across a number of fast-food restaurants. While fast food is convenient and affordable, it can also be incredibly unhealthy. We were interested in understanding the nutritional impact fast food consumption has and how we can pursue healthier food options within the fast-food industry. We sought to answer the following questions:
•	If you’re going to eat fast food, what is the best restaurant to eat at regarding recommended dietary values? 
•	In regards to calories, fat and protein, how do items at one fast food restaurant compare with menus of other fast-food restaurants?
•	What items at which restaurant fall within the suggested daily caloric intake averages and are still high in protein to keep you filled up?

## Key nutrients and their relationship to calories
We sorted each category - calories, protein, fat, sodium, sugar - by their minimum and maximum values and grouped this information by restaurant to better understand the range of menu items each venue offered. We then wanted to understand the relationship each key nutrient played to calories. Being that calories are an overarching unit, we wanted to know how protein, fat, sodium and sugar influenced this value. We found no one key nutrient had a linear relationship. As well as the fact that McDonald's has outliers across all categories.  

## Looking at items by calorie groupings and identifying low calorie, high protein menu items
In order to find lower calorie options that were also high in protein we first started by creating a data frame suggested daily intake values for both females and males based on information from U.S. Food and Drug Administration, Office of Disease Prevention and Health Promotion, and Cleveland Clinic. The initial data frame broke out the values for calories, total fat, saturated fat, cholesterol, sodium, carbohydrates, fiber, sugar, and protein by male and female. From there, we created separate variables for suggested caloric intake per meal by sex. Using these new caloric intake variables, we were able to look through the data and find items within the suggested allotment that also had greater than or equal 30g of protein, suggesting these are items that might keep a person fuller for longer and potentially making them a strong choice on the menus. By comparing these options across restaurants and by sex we found that there were 122 options that fell within the parameters for males and 57 for females, which was substantially more than originally anticipated. McDonalds and Subway have the most options for both males and females.
The majority, 82.2%, of items across all restaurants actually contain less than 749 calories with the median being 490 calories. We created bins to group items into calorie ranges by groups of 250 calories. By creating the bins, we were easily able to see that many of the items were within a fairly normal caloric intake range per meal. By calculating the upper, lower, interquartile ranges we were able to identify that calorie values above 1222.5 calories could be considered outliers. We also looked at the averages for calories, fat, cholesterol, sodium, carbohydrates, and protein across each calorie range. 
We looked at the correlation coefficients for a number of variables and found that calories and cholesterol, calories and carbohydrates, and calories and fat are fairly strongly correlated at 0.76, 0.71, and 0.9 respectively. 


## Comparing Fast Food Restaurants to Cooking at Home
We analyzed how different fast food restaurants stack up to cooking at home with accessible recipes online by using Spoonacular's API to pull in a random recipe that is within a 5% range of the fast food items calorie count. Each recipe from Spoonacular includes calories, protein, carbs, and fat content.

Spoonacular only allows 149 free API calls a day, so we cleaned our data to have a relatively even split of 6 fast food restaurants for a total of 149. Then a random spoonacular recipe within the calorie range was attached. 

Next, we ran a two tailed T-Test comparing the average for each fast food restaurant against the average from the associated random recipes for a given nutrient. The output is found in t_test_df. This gives a good look at which restaurants have a statistically significant nutrient differences from the associated recipes. The one that jumps out the most is Subway as it is the only restaurant that has a p-value below the alpha of 0.05 for protein, carbs, and fat. Outside of Taco Bell, which had statistical difference for carbs and fat, all other restaurants showed no statistical difference for any of the nutrients, leading us to beleive that an occassionaly meal at one of these establishments is okay if for a diet concerened with these nutrients.

However, we wanted to look at which restaurants had statistically significant negative differences to random online recipes. To do this, we need to treat our nutrients differently in the T-Test because for protein we may want to understand which fast food restaurant is on average lower than random recipes whereas with carbs we would like to know which is higher on average that random recipes. The function nutrition_recipe_analysis() allows a user to input a restaurant, nutrient, and alternative hypothesis they would like to test in order to answer these questions.

***alpha = 0.05 for all T-Tests***
