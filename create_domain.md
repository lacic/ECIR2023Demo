### Create a new domain for MovieLens

After a successful log-in, you will see an overview of previously created application domains.

By clicking on the "**+ Domain**" button, you can create a new domain on the **system-level**.

<p align="center">
<img src="/images/add_domain.png" alt="Add domain" height="400">
</p>

Every domain has to have a **unique name** assigned to it.  
This name will be used to create a **unique** **Domain-ID** that needs to be provided
as a parameter to the auto-generated data upload and recommendation APIs.

<p align="center">
<img src="/images/create_domain_name.png" alt="Create domain" height="200">
</p>


After successfully creating the **MovieLens** domain, you will end up on the **Data Catalog** view.


<p align="center">
<img src="/images/configure_data.png" alt="Configure data" height="400">
</p>

Within the **Data Catalog** view, you need to first:
1. [Configure the Item API](configure_item_data.md)
2. [Configure the User API](configure_user_data.md)
3. [Configure the Interaction API](configure_interactions_data.md)

After this has been done, you need to click on "**Deploy Services**".

This will prepare the auto-generated API which you can use in [Data Upload notebook](notebooks/Data_Upload.ipynb) to upload the data
that is needed for you recommendation models.

<p align="center">
<img src="/images/data_api.png" alt="Configure data api" height="450">
</p>

>Please note that the appropriate **API-Key** and **Domain-ID**, which are shown
in the Uptrendz platform **for your own user account**, need to be used when integrating the respective data ingestion API to upload the data.
