### Configure the User API

The first thing that needs to be defined is the entity which will be recommended.
In the case of the MovieLens-100k dataset, we know that are entity is called "**user**".

<p align="center">
<img src="/images/configure_user_type.png" alt="Add user" height="200">
</p>

> Please note that by adding **multiple user entities**, you are defining multiple domains on an **item-level**.


By creating a new entity, we can define what kind of meta-data that particular entity has available.
In the **Uptrendz platform**, the following attribute types are supported when the data model for user entities:

|      Field Type       |  Field Subtype  | Description                                                                                                                                   |
|:---------------------:|:---------------:|-----------------------------------------------------------------------------------------------------------------------------------------------|
|   Categorical Text    |  Single Value   | String value which usually depict some kind of category. Most commonly used for post-filtering recommendation results.                        |
|   Categorical Text    | Multiple Values | Array of string values which usually depict some kind of category. Most commonly used for post-filtering  recommendation results.             |
|       Free Text       |     English     | Text that should be processed and utilized for content-based recommendation. Language of the text shoud be English.                           |
|       Free Text       |     German      | Text that should be processed and utilized for content-based recommendation. Language of the text shoud be German.                            |
|        Numeric        |     Integer     | Integer number which usually depict some kind of value (e.g., age of a user). Most commonly used for post-filtering recommendation results.   |
|        Numeric        |      Real       | Real number which usually depict some kind of value (e.g., price of a product). Most commonly used for post-filtering recommendation results. |
|         Date          |        -        | Date information for the respective entity (e.g., created date). Expected format: _YYYY-MM-DDThh:mm:ssZ_                                      |

#### MovieLens-100k configuration

Given the MovieLens-100k dataset, the following **user configuration** should be defined for the **User API**:

| Field Name |    Field Type    | Field Subtype |
|:----------:|:----------------:|---------------|
|     id     | Categorical Text | Single Value  |
|    age     |     Numeric      | Integer       |
|   gender   | Categorical Text | Single Value  |
| occupation | Categorical Text | Single Value  |
|    zip     | Categorical Text | Single Value  |


<p align="center">
<img src="/images/configure_user_data.png" alt="Add user data" height="350">
</p>

Once the **User API** is prepared, we can upload **user data** 
using the [Data Upload notebook](notebooks/Data_Upload.ipynb).
