# Indian Cuisine Analysis 
### Team 14: Sebastian Khattabi, Abby Kisicki, Andrew Tenjum

## Introduction: 
With nearly 80,000 Indian restaurants in the United States, Indian cuisine has cemented itself in the cultural food landscape as food that is complex, fulfilling, and exciting. India has aptly been called “The Land of Spices,” and no other country can purport similar claims. No country in the world produces as many varieties of spices as India. With a history rooted in colonialism and such a diverse ethnic makeup, India’s food is complex to say the least. But what makes a dish inherently “Indian?” Is it the ingredients in the dish? Is it the way the dish is prepared? Is it the origin of the dish? Is it the flavor profile of the dish? There are so many questions to consider when considering this deep dive analysis into Indian cuisine. 
 
We intend to communicate existing knowledge of Indian cuisine in a new way. As Indian food continues to rise in popularity, chefs, cooks, food scientists, restaurateurs, and even retail owners need to have an in-depth understanding of Indian cuisine. At the end of this group project, we hope that the (non-statistics) professionals mentioned earlier can simply look at our data visualizations and gain a deeper understanding of Indian food.

## Data Sources: 
Our analysis will be based on a dataset of 255 Indian dishes that contains a list of ingredients, type of diet (vegetarian or non-vegetarian), preparation and cook time, flavor profile, type of course, and the state/region where the dish originated. The original dataset can be found [here](https://www.kaggle.com/nehaprabhavalkar/indian-food-101). 

## Visualization #1:

[Link to Visualization #1](https://observablehq.com/@seabass394/indian-recipes-map)

## Visualization #2:

[Description of Visualization #2]
Our second visualization attempts to identify similarities between dishes based on the ingredients they contain. A network was implemented using a node-link diagram. The nodes in the network represent different dishes while the edges between nodes represent whether dishes contain more than 1 common ingredient. Furthermore, the edge weights represent the number of ingredients shared by dishes. 

![Whole Net](https://user-images.githubusercontent.com/83096602/117506041-92301f00-af4a-11eb-845f-f3ffa15a2e8b.png)

![Bigger Dense 1](https://user-images.githubusercontent.com/83096602/117506316-01a60e80-af4b-11eb-92f4-96c371f559f4.png)

![Bigger Dense 2](https://user-images.githubusercontent.com/83096602/117506378-1b475600-af4b-11eb-9255-9ae9a1f42b00.png)

![Less Dense](https://user-images.githubusercontent.com/83096602/117506574-6b261d00-af4b-11eb-9ac9-a238ffed51e3.png)

[Interpretations of Visualization #2]
From this diagram, we can identify clusters of dishes that share ingredients. For example, at the top of the diagram we can see a distinct cluster of dishes with common ingredients, including several dishes that share large numbers of ingredients. The cluster at the bottom of the diagram also contains dishes with similar ingredients, but this cluster is more spread out, meaning that the dishes are collectively less similar to each other and also share lesser numbers of ingredients on average. Finally, on the sides of the diagram we see dishes that are more isolated, meaning their ingredient profile is relatively unique. A goal in the next implementation will be to make the diagram more interpretable by excluding dishes that share small numbers of ingredients and utilizing color to add more descriptive details.

## Visualization #3:

Our 3rd visualization is a principal component analysis of the 255 Indian food recipes. The principal components are derived from the 366 unique ingredients which are coded as binary dummy variables. By reducing the 366 features (ingredients) into just a few principal components, we are able to condense large amounts of information while minimizing information. The top 2 principal components are shown below.
![PC1 and PC2](https://user-images.githubusercontent.com/83096602/117506860-e38cde00-af4b-11eb-90ff-633f31971088.png)
Looking at the top 2 principal components, we can identify what ingredients are likely and unlikely to be in dishes that have high values for each principal component. For example, we see that dishes with high values of PC1 are unlikely to contain ginger, urad dal, curry leaves, mustard oil, tomatoes, or mustard seeds, but are likely to contain gur and gram flour. We would expect gur and gram flour to show up primarily in sweet foods, so it’s likely that PC1 is correlated with sweetness. Dishes with high values of PC2 are unlikely to contain gur, arbi ke patte, gram flour, or sesame seeds, but are likely to contain tomatoes and mustard oil. Therefore, we would expect dishes with high PC2 values to be less sweet and more spicy or savory in general.
![PC1 vs. PC2](https://user-images.githubusercontent.com/83096602/117508991-171d3780-af4f-11eb-9d0c-ebfde1bb4741.png)
We then plotted PC1 values vs. PC2 values for each dish and colored each of these data points according to whether the dish is sweet or spicy. Because we expected PC1 to be correlated with sweetness and PC2 to be associated with spicy or savory, we would expect an overall negative correlation between PC1 and PC2. The plot indeed shows a (weak) negative correlation. Sweet foods (shown as blue points) tend to have high values of PC1, which matches our initial hypothesis that PC1 was correlated with sweetness. Similarly, spicy foods (shown as red points) tend to have low values of PC1, which makes sense if PC1 is associated with sweetness. Generalizing PC2 is less clear because both sweet foods and spicy foods have varying values of PC2. From this we can glean that PC2 is likely comprised  of ingredients that are used in both sweet and spicy foods.





