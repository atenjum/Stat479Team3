# Indian Cuisine Analysis 
### Team 14: Sebastian Khattabi, Abby Kisicki, Andrew Tenjum

## Introduction: 
With nearly 80,000 Indian restaurants in the United States, Indian cuisine has cemented itself in the cultural food landscape as food that is complex, fulfilling, and exciting. India has aptly been called “The Land of Spices,” and no other country can purport similar claims. No country in the world produces as many varieties of spices as India. With a history rooted in colonialism and such a diverse ethnic makeup, India’s food is complex to say the least. But what makes a dish inherently “Indian?” Is it the ingredients in the dish? Is it the way the dish is prepared? Is it the origin of the dish? Is it the flavor profile of the dish? There are so many questions to consider when considering this deep dive analysis into Indian cuisine. 
 
We intend to communicate existing knowledge of Indian cuisine in a new way. As Indian food continues to rise in popularity, chefs, cooks, food scientists, restaurateurs, and even retail owners need to have an in-depth understanding of Indian cuisine. At the end of this group project, we hope that the (non-statistics) professionals mentioned earlier can simply look at our data visualizations and gain a deeper understanding of Indian food.

## Data Sources: 
Our analysis will be based on a dataset of 255 Indian dishes that contains a list of ingredients, type of diet (vegetarian or non-vegetarian), preparation and cook time, flavor profile, type of course, and the state/region where the dish originated. The original dataset can be found [here](https://www.kaggle.com/nehaprabhavalkar/indian-food-101). 

## Visualization #1:

Our first visualization attempts to pinpoint the geographic states of India to specific recipes in which they originate from. These map visualizations are our only interactive plots. We are implementing a tooltip in which when the cursor is hovering over a state it will stay the state name as well as specific features of the region. We plan to have in total 4 different maps of India that go over the following attributes: number of recipes, average total time, proportion of spicy recipes, and then proportion of vegetarian recipes.

[Link to Visualization #1](https://observablehq.com/@seabass394/indian-recipes-map)

The link to the observable notebook above shows these map visualizations as well as possible interpretations. 

## Visualization #2:

Our second visualization attempts to identify similarities between dishes based on the ingredients they contain. A network was implemented using a node-link diagram. The nodes in the network represent different dishes while the edges connect dishes that share two or more ingredients. The edge weights represent the number of ingredients shared by dishes. 

![Complete](https://user-images.githubusercontent.com/83096602/117522501-6bd5a800-af79-11eb-92aa-6145e991e324.png)

In the following three figures, three different close-ups of the network are shown (Figure A, Figure B, and Figure C). The following image is the complete view of the network overlaid with a guide to the different areas for which we have generated close-up images.

![Callout](https://user-images.githubusercontent.com/83096602/117522507-77c16a00-af79-11eb-8ba9-77644b2b39ed.png)

![Figure A](https://user-images.githubusercontent.com/83096602/117522509-7c861e00-af79-11eb-8a45-8bb52d4558f8.png)

From this diagram, we can identify clusters of dishes that share ingredients. For example, the cluster at the bottom of the diagram contains dishes with similar ingredients, but this cluster is more spread out, meaning that the dishes are collectively less similar to each other and also share fewer ingredients on average. Finally, on the sides of the diagram we see dishes that are isolated and have few connections, meaning their ingredient profile is relatively unique. 

![Figure B](https://user-images.githubusercontent.com/83096602/117522510-827bff00-af79-11eb-9c9f-e7bf2887396c.png)

At the top of the diagram we can see a distinct cluster of dishes with common ingredients, including several dishes that share many ingredients with many other dishes. In addition to the tightly packed shape of this area, this means that these recipes are very similar to one another. 

![Figure C](https://user-images.githubusercontent.com/83096602/117522512-86a81c80-af79-11eb-9e4f-391b9b9d43c7.png)

As many of the recipes in this tightly packed, highly connected area contain sugar, flour, and ghee (clarified butter), we suspect that this group of recipes represents baked goods or pastries, which are necessarily quite similar to each other in terms of ingredients.


## Visualization #3:

Our 3rd visualization is a principal component analysis of the 255 Indian food recipes. The principal components are derived from the 366 unique ingredients which are coded as binary dummy variables. By reducing the 366 features (ingredients) into just a few principal components, we are able to condense large amounts of information into a more interpretable form while minimizing information loss. The top 2 principal components are shown below.
![PC1 and PC2](https://user-images.githubusercontent.com/83096602/117506860-e38cde00-af4b-11eb-90ff-633f31971088.png)

Looking at the top 2 principal components, we can identify what ingredients are likely and unlikely to be in dishes that have high values for each principal component. For example, we see that dishes with high values of PC1 are unlikely to contain ginger, urad dal, curry leaves, mustard oil, tomatoes, or mustard seeds, but are likely to contain gur and gram flour. We would expect gur and gram flour to show up primarily in sweet foods, so it’s likely that PC1 is correlated with sweetness. Dishes with high values of PC2 are unlikely to contain gur, arbi ke patte, gram flour, or sesame seeds, but are likely to contain tomatoes and mustard oil. Therefore, we would expect dishes with high PC2 values to be less sweet and more spicy or savory in general.
![PC1 vs. PC2](https://user-images.githubusercontent.com/83096602/117508991-171d3780-af4f-11eb-9d0c-ebfde1bb4741.png)

We then plotted PC1 values vs. PC2 values for each dish and colored each of these data points according to whether the dish is sweet or spicy. Because we expected PC1 to be correlated with sweetness and PC2 to be associated with spicy or savory, we would expect an overall negative correlation between PC1 and PC2. The plot indeed shows a (weak) negative correlation. Sweet foods (shown as blue points) tend to have high values of PC1, which matches our initial hypothesis that PC1 was correlated with sweetness. Similarly, spicy foods (shown as red points) tend to have low values of PC1, which makes sense if PC1 is associated with sweetness. Generalizing PC2 is less clear because both sweet foods and spicy foods have varying values of PC2. From this we can glean that PC2 is comprised primarily of ingredients that are used in both sweet and spicy foods.

The major takeaway from this analysis is that we can use principal component analysis 
to group together foods with similar flavor profiles. Instead of analyzing all 366 possible
ingredients, we can instead analyze the principal components that are made up of those 
Ingredients in order to learn more about what ingredients make up different flavor profiles in Indian food.
