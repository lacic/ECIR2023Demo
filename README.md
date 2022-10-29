# ECIR 2023 Demo Paper Track

This repository accompanies the paper 
"**A Multi-Domain System for Real-time Recommendations**" 
submitted to ECIR'23 Demonstration Paper Track.

**DEMONSTRATION GOAL:** Setup an online movie recommender


The purpose of the following content is to show how a real-time movie recommender could be setup up and used in an online setting. 

For this, we will use the [MovieLens 100k dataset](http://files.grouplens.org/datasets/movielens/ml-100k/) but the same 
workflow can be done for any other 
domain that contains item, user or interaction data.

In the **Uptrendz platform**, there are multiple ways on how to configure a **multi-domain recommender system**. <br/>
It is possible to create a domain on a **system level** (i.e., **data** between domains is **separated** and **not shared**) or on an **item level** (i.e., **data** is **shared** between domains). 
In this repository, we will create a movie recommender on the **system level**.

### Domain setup and usage of the Uptrendz platform:
1. Go to [uptrendz.ai](http://uptrendz.ai)
   * Register a new user account or log-in using your existing Google account
2. [Create a new domain for MovieLens](create_domain.md)
   * We create a domain on the system-level
3. [Configure the Item API](configure_item_data.md)
   * Need to define what meta-data is available for movies
4. [Configure the User API](configure_user_data.md)
   * Need to define what meta-data is available for users
5. [Configure the Interaction API](configure_interactions_data.md)
   * Need to define that we are using explicit rating interactions
6. [Create recommendation scenarios](configure_reco_scenarios.md) 
   * Need to create recommendation APIs with desired algorithms and post-processing rules 
7. Run the provided [notebooks](notebooks/) to:
    * Upload the data (i.e., movies, users and ratings) to your newly created movie domain
        * Using the auto-generated data ingestion APIs
    * Request recommendations for the constructed recommendation scenario
        * Using the auto-generated recommendation APIs  

**Prerequisite:**

In order to run the notebooks provided in this repository, you need to have a working jupyter notebook environment.
In case you don't have one, the easiest way is to use pre-built docker images.

Example on [Windows 11 with Ubuntu 20.04 using WSL2](https://ubuntu.com/tutorials/install-ubuntu-on-wsl2-on-windows-11-with-gui-support#1-overview) and installed **docker 20.10.18**:
* Open Terminal
* If docker is not running, run `sudo dockerd`
* Run `docker pull jupyter/scipy-notebook` to retrieve the appropriate image
* Run `docker run -it --rm -p 8888:8888 -v "$PWD"/notebooks/:/home/jovyan/ jupyter/scipy-notebook`
* Open Jupyter lab by typing [localhost:8888](localhost:8888) in your browser (token password should be displayed in the terminal)
