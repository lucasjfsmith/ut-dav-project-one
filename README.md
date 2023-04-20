# ut-dav-project-one
Analyze fast food data from different popular restaraunts based on nutritional value.

### Team Members:
Luke Smith
Kim Reitema
Donna Das
Shahad Rahman

## Comparing Fast Food Restaurants to Cooking at Home
We analyzed how different fast food restaurants stack up to cooking at home with accessible recipes online by using Spoonacular's API to pull in a random recipe that is within a 5% range of the fast food items calorie count. Each recipe from Spoonacular includes calories, protein, carbs, and fat content.

Spoonacular only allows 149 free API calls a day, so we cleaned our data to have a relatively even split of 6 fast food restaurants for a total of 149. Then a random spoonacular recipe within the calorie range was attached. 

Next, we ran a two tailed T-Test comparing the average for each fast food restaurant against the average from the associated random recipes for a given nutrient. The output is found in t_test_df. This gives a good look at which restaurants have a statistically significant nutrient differences from the associated recipes. The one that jumps out the most is Subway as it is the only restaurant that has a p-value below the alpha of 0.05 for protein, carbs, and fat. Outside of Taco Bell, which had statistical difference for carbs and fat, all other restaurants showed no statistical difference for any of the nutrients, leading us to beleive that an occassionaly meal at one of these establishments is okay if for a diet concerened with these nutrients.

However, we wanted to look at which restaurants had statistically significant negative differences to random online recipes. To do this, we need to treat our nutrients differently in the T-Test because for protein we may want to understand which fast food restaurant is on average lower than random recipes whereas with carbs we would like to know which is higher on average that random recipes. The function nutrition_recipe_analysis() allows a user to input a restaurant, nutrient, and alternative hypothesis they would like to test in order to answer these questions.

***alpha = 0.05 for all T-Tests***