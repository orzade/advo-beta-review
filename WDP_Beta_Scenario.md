# Scenario: LocalCart seeks to boost sales by better understanding their customers

LocalCart is a grocery delivery service that prides itself on its relationships with local businesses. Users order specialty products and regular groceries from LocalCart’s website, and the items arrive the same day — even within the hour.  
  
To be successful, LocalCart requires a deep understanding of who their customers are, the behavior of those customers when shopping through LocalCart, and the ability to provide targeted product recommendations to increase revenue. 


## LocalCart's data analysis needs
LocalCart has identified three key data and analytics projects that they want to start as soon as possible. LocalCart is looking for a single cloud data and analytics platform that will enable them to quickly and easily deliver all three projects. 

LocalCart wants:

* Real-time (streaming) aggregated customer activities with intraday revenue figures and real-time funnel status.
* Customer behavior information, such as demographics, shopping cart values, and so on.
* A recommendation engine to encourage additional purchases based on past buying behavior.

Using functionality available in Watson Data Platform, LocalCart's data scientists and application developers create assets in the form of Jupyter notebooks. Notebooks can include text instructions, runnable code, and output including charts and graphs.  

IBM Watson Data Platform provides LocalCart with a single cloud platform for app deployment, data management, streaming analytics, machine learning, and more. Follow along as we create the deliverables that address LocalCart's needs by using Watson Data Platform.

LocalCart solution architecture:
![Diagram of architecture](./images/beta-architecture.jpg "Solution architecture")

### Prerequisites

If you followed the instructions in your welcome letter, you should already have your Bluemix ID and be logged in to Data Science Experience. The services you need to complete this tutorial were already created for you, and you have the keys to your Spark service and Object Storage.

As part of the beta program setup, you already have a set of services and applications available. These include:

* Data Science Experience
* IBM Watson Machine Learning
* Message Hub
* Cloudant NoSQL DB
* Compose for PostgreSQL
* Compose for Redis
* Data Connect
* Db2 on Cloud

Find overview and getting-started information, including how to set up a project, in the Data Science Experience documentation: https://datascience.ibm.com/docs/content/getting-started/welcome-main.html. 

Learn about Jupyter notebooks, which are used throughout this scenario, in the Data Science Experience documentation: https://datascience.ibm.com/docs/content/analyze-data/notebooks-parent.html

### Creating your first project and notebook

1. Log in to Data Science Experience https://datascience.ibm.com.
1. Set up a project in Data Science Experience, and link your Spark service and Object Storage to that project: 
	1. 	Click **Get started**, then click **New project**. 
	1. Enter a name for your project, select your Spark service, Object Storage instance, and click **Create**.
1. In your new project, click **Add to project > Notebook**.
	1. Click **From URL**. 
	1. Enter a notebook name, optional description, and the URL to Notebook 1: https://github.com/wdp-beta/get-started/blob/master/notebooks/localcart-scenario-part-1.ipynb .
1. Click **Create Notebook**.
1. Follow the scenario that follows, starting in *Notebook 1, LocalCart scenario part 1: Creating a Kafka Producer of clickstream events*. 


### Aggregating and analyzing customer activity data

To address LocalCart's first project goal, their data science team collects data from their application clickstream and saves it to a database for analysis. You can simulate the streaming data capture by running the following notebooks:

1. **Streaming data producer**. Build a clickstream event generator to provide streaming data, which is then archived in REDIS for later analytics processing. [LocalCart scenario part 1: Creating a Kafka Producer of clickstream events](https://github.com/wdp-beta/get-started/blob/master/notebooks/localcart-scenario-part-1.ipynb)
1. **Streaming data pipeline**. Build the streaming pipeline that monitors intraday revenue. [LocalCart scenario part 2: Creating a streaming pipeline](https://github.com/wdp-beta/get-started/blob/master/notebooks/localcart-scenario-part-2.ipynb)
1. **MessageHub to CSV streaming pipelines**. Capture streaming data and write it to CSV files for analysis. [LocalCart scenario part 2b: MessageHub to CSV streaming pipelines](https://github.com/wdp-beta/get-started/blob/master/notebooks/localcart-scenario-part-2b.ipynb)

### Exploring and analyzing customer activity data

Next the LocalCart team learns more about their customers by examining their demographics, and then digs into sales transactions. Developing customer behavior analytics requires two separate but related skillsets: the data engineer, and the data scientist.

Just as they collaborated using notebooks, you can use their notebooks to run their work for yourself:

1. **Customer data exploration and analysis**. Build an analysis that ingests and prepares data and transforms the data for use by the data scientists. 

	* [LocalCart scenario part 3: Analyze customer demographics and sales data](https://github.com/wdp-beta/get-started/blob/master/notebooks/localcart-scenario-part-3.ipynb)

	* [LocalCart scenario part 3b: Static clickstream analysis](https://github.com/wdp-beta/get-started/blob/master/notebooks/localcart-scenario-part-3b.ipynb)


2. **Customer activity dashboard** Create a dashboard that visualizes real-time aggregated data from clickstream, including:
	* Aggregated customer activities  
	* Revenue figures on 5-minute sliding window  
	* Real-time funnel status
	* [LocalCart scenario part 4: Visualize streaming data in a real-time dashboard](https://github.com/wdp-beta/get-started/blob/master/notebooks/localcart-scenario-part-4.ipynb)


### Recommending additional purchases

Finally, build a recommendation engine that will encourage LocalCart customers to buy additional products. Recommendations will be based on individual customer buying behavior, all-customers buying behaviors across the LocalCart business, and product rating. 

* **A recommendation engine using Watson Machine Learning**. [LocalCart scenario part 5: Recommending purchases](https://github.com/wdp-beta/get-started/blob/master/notebooks/localcart-scenario-part-5.ipynb).

The developer or data scientist: 

1. Builds, trains, and tests a recommendation engine model with SparkML.
1. Deploys the model, which generates an API that can be called by the LocalCart application.
1. Runs the deployed model API.
1. Presents results in a simulated application.


  






