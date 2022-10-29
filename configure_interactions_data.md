### Configure the Interaction API

Once the [Item API](configure_item_data.md) and [Item API](configure_user_data.md) is defined, 
we need to define the API to send **user interactions**. 


The Uptrendz platform supports:
* interactions for **anonymous** user sessions, **registered** users or **both**
* **user-item** and **user-user** interactions in this regard.
* **implicit** interactions (e.g., click) or **explicit** interactions (e.g., ratings)
     * In case of explicit interactions, it is needed to define the **value interval** (e.g., [1,5])
     * The number of different interaction types is **not restricted** (i.e., we can define as many interaction types as we want)
* if a timestamp is not provided, it is created automatically when the interaction is received

#### MovieLens-100k configuration

In the case of the MovieLens-100k dataset, we need to define an **Interaction API** for:
* User Types = **Registered Users**
* User-to-User interactions = **No** (i.e., only user-item interactions are available in the MovieLens-100k dataset)
* Time Tracking = **yes** (i.e., timestamps are available in the MovieLens-100k dataset)
* Interaction Type = "**rating**"
    * With a rating scale from 1 to 5 that is available in the MovieLens-100k dataset


<p align="center">
<img src="/images/configure_interactions.png" alt="Add interactions" height="350">
</p>

Once the **User API** is prepared, we can upload **interaction data** 
using the [Data Upload notebook](notebooks/Data_Upload.ipynb).
