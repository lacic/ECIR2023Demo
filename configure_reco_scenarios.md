### Create recommendation scenarios

Once, the [MovieLens domain has been configured](create_domain.md), 
we can demonstrate how to use the **Engine Console** in Uptrendz to provide **recommendation APIs** in an online setting.

For this demo, we will use four movie recommendation approaches that are based on:
* [Popularity with post-filtering on movie genre](#popularity-with-post-filtering-on-movie-genre)
* [Collaborative-Filtering using rating data](#collaborative-filtering-using-rating-data)
* [Content-Based Filtering using the title attribute](#content-based-filtering-using-the-title-attribute)
* [Weighted Hybrid](#weighted-hybrid)

<p align="center">
<img src="/images/scenarios.png" alt="Scenarios" height="400">
</p>

Each of the generated APIs can then be used to request recommendations as
demonstrated in the  [Recommendation Scenarios notebook](notebooks/Recommendation_Scenarios.ipynb).

To create a recommendation API to serve recommendations, 
the Uptrendz platform fosters the notion of defining 
**personalization scenarios** (i.e., use-cases). 
Each scenario will have an auto-generated **Scenario ID** which needs 
to be provided when calling the recommendation API.

<p align="center">
<img src="/images/most_popular.png" alt="Popularity" height="200">
</p>


The available selection of real-time recommendation models for a 
given scenario depends on:
* What should be recommended?
    * E.g., item or user entities
* For whom are the recommendations targeted?
    * E.g., registered or anonymous users 
* What kind of context is available?
    * E.g., ID of the item for which we want to recommend relevant content


#### Popularity with post-filtering on movie genre

Scenario Name: **Popular Horror Movies**
* Auto-generated Scenario ID: **popular-horror-movies**

What will be recommended: **movie** <br/>
What will be recommended: **ItemMP** <br/>
Item Context: **none** <br/>
Popularity calculated using: **ratings**<br/>
Consideration Of Consumed Items: **none**
* We recommend movies, regardless if the user has already interacted with them or not

To demonstrate how to create a scenario that does a post-filtering step, 
we define a business rule that defines to only recommend movies, which have the "**horror**" 
value as part of their **genre** attribute.

<p align="center">
<img src="/images/most_popular_business_rules.png" alt="Popularity" height="350">
</p>


#### Collaborative-Filtering using rating data

Scenario Name: **Movies based on my ratings**
* Auto-generated Scenario ID: **movies-based-on-my-ratings**

What will be recommended: **movie** <br/>
What will be recommended: **InteractionCf** <br/>
Item Context: **none** <br/>
User history fetched using: **ratings**  <br/>
User neighborhood calculated using: **ratings**
* We can add a weight of **1** as there are no other interaction types in the MovieLens-100k dataset

Consideration Of Consumed Items: **none**
* We recommend movies, regardless if the user has already interacted with them or not


<p align="center">
<img src="/images/collaborative_movies.png" alt="Collaborative" height="350">
</p>

#### Content-Based Filtering using the title attribute

Scenario Name: **Similar Movies**
* Auto-generated Scenario ID: **similar-movies**

What will be recommended: **movie** <br/>
What will be recommended: **ItemCb** <br/>
Item Context: **movie** <br/>
Consideration Of Consumed Items: **none**
* We recommend movies, regardless if the user has already interacted with them or not


<p align="center">
<img src="/images/similar_movies.png" alt="Similar" height="300">
</p>


This recommendation API will need to have an existing **movie ID** provided.
In order to calculate similarity based on the content, we need to define 
which textual field will be used for that. In this demonstration we use
the **title** attribute. 


<p align="center">
<img src="/images/similar_movies_config.png" alt="Similar Config" height="350">
</p>

#### Weighted Hybrid

Scenario Name: **Hybrid Combination**
* Auto-generated Scenario ID: **hybrid-combination**

What will be recommended: **movie** <br/>
What will be recommended: **HybridRoundRobinWeightedSum** <br/>
Item Context: **none** <br/>

<p align="center">
<img src="/images/hybrid_movies.png" alt="Hybrid" height="350">
</p>


#### User recommendation

<p align="center">
<img src="/images/users_for_movies.png" alt="User" height="350">
</p>

