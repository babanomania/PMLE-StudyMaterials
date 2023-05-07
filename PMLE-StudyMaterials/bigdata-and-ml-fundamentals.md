# [Google Cloud Big Data and Machine Learning Fundamentals](https://www.youtube.com/playlist?list=PLtYQVzxMLm3k0TYSJtxiCdf2cReEdxLha)

- [Big Data and Machine Learning on the Google Cloud](#big-data-and-machine-learning-on-the-google-cloud)
  * [Introduction](#introduction)
  * [Compute](#compute)
  * [Storage](#storage)
  * [The history of big data and ML products](#the-history-of-big-data-and-ml-products)
  * [Big data and ML product categories](#big-data-and-ml-product-categories)
  * [Customer example Gojek](#customer-example-gojek)
  * [Getting Started with Google Cloud Platform and Qwiklabs](#getting-started-with-google-cloud-platform-and-qwiklabs)
  * [Lab introduction Exploring a BigQuery Public Dataset](#lab-introduction-exploring-a-bigquery-public-dataset)
  * [Summary](#summary)
- [Data Engineering for Streaming Data](#data-engineering-for-streaming-data)
  * [Introduction of Data Engineering for streaming data](#introduction-of-data-engineering-for-streaming-data)
  * [Big Data Challenges](#big-data-challenges)
  * [Message oriented architecture](#message-oriented-architecture)
  * [Designing streaming pipelines with Apache Beam](#designing-streaming-pipelines-with-apache-beam)
  * [Implementing streaming pipelines on Cloud Dataflow](#implementing-streaming-pipelines-on-cloud-dataflow)
  * [Visualization with Looker](#visualization-with-looker)
  * [Visualization with Data Studio](#visualization-with-data-studio)
  * [Lab introduction Creating a streaming data pipeline for a Real Time dashboard with Dataflow](#lab-introduction-creating-a-streaming-data-pipeline-for-a-real-time-dashboard-with-dataflow)
  * [Summary of Second section](#summary-of-second-section)
- [Big Data with BigQuery](#big-data-with-bigquery)
  * [Introduction](#introduction-1)
  * [Storage and analytics](#storage-and-analytics)
  * [BigQuery demo - San Francisco bike share](#bigquery-demo---san-francisco-bike-share)
  * [Introduction to BigQuery ML](#introduction-to-bigquery-ml)
  * [Using BigQuery ML to predict customer lifetime value](#using-bigquery-ml-to-predict-customer-lifetime-value)
  * [BigQuery ML Project Phases](#bigquery-ml-project-phases)
  * [BigQuery ML key commands](#bigquery-ml-key-commands)
  * [Summary](#summary-1)
- [Machine Learning Options](#machine-learning-options)
  * [Introduction](#introduction-2)
  * [Options to build ML models](#options-to-build-ml-models)
  * [Pre built APIs](#pre-built-apis)
  * [AutoML](#automl)
  * [Custom Training](#custom-training)
  * [Vertex AI](#vertex-ai)
  * [AI Solutions](#ai-solutions)
  * [Summary](#summary-2)
- [The Machine Learning Workflow with Vertex AI](#the-machine-learning-workflow-with-vertex-ai)
  * [Introduction](#introduction-4)
  * [Data Preparation](#data-preparation)
  * [Model Training](#model-training)
  * [Model Evaluation](#model-evaluation)
  * [Model Deployment and Monitoring](#model-deployment-and-monitoring)
  * [Lab introduction: Predicting loan risk with AutoML](#lab-introduction-predicting-loan-risk-with-automl)
  * [Lab recap Predicting loan risk with AutoML](#lab-recap-predicting-loan-risk-with-automl)
  * [Summary](#summary-3)
- [Course Summary](#course-summary)


## Big Data and Machine Learning on the Google Cloud

### Introduction

- Google has been working with data and AI since 1998, and in 2008, Google Cloud platform was launched to provide cloud computing and storage services.
- Google Cloud infrastructure can be thought of in three layers:
- Networking and security (base layer)
- Compute and storage (middle layer)
- Big data and machine learning products (top layer)
- Compute and storage layer is decoupled, which means they can scale independently based on needs.
- The top layer includes big data and machine learning products that allow performing tasks like ingest, store, process and deliver business insights, data pipelines and ML models.
- The course focuses on the middle and top layers, compute and storage, and big data and machine learning products.
- The course includes exploring the history of big data and ML products to understand relevant product categories, and a customer example of adapting Google Cloud for big data and ML needs.
- Hands-on practice using big data tools is provided to analyze a public data set.
- To learn more about networking and security, check cloud.google.com/training.

### Compute
- Google Cloud Infrastructure has three main computing services: Compute Engine, Google Kubernetes Engine (GKE), and App Engine.
- Compute Engine provides virtual compute and storage resources that are similar to physical data centers, giving maximum flexibility to those who prefer to manage server instances themselves.
- GKE runs containerized applications in a cloud environment, using containers to package code with all its dependencies, and is more scalable than Compute Engine.
- App Engine is a fully managed platform-as-a-service offering that allows for more resources to be focused on application logic by binding code to libraries that provide access to the infrastructure application needs.
- Cloud Functions is a completely serverless execution environment that executes code in response to events and is often referred to as functions as a service.
- Cloud Run is a fully managed compute platform that enables users to run requests or event-driven stateless workloads without having to worry about servers, automatically scaling up and down as needed.
- Google Photos relies on the compute capability provided by Google Cloud to implement their video stabilization feature, which uses a high-performing machine learning model trained on millions of videos.
- To train sophisticated machine learning models, Google uses a vast network of data centers and a custom-developed application-specific integrated circuit called the Tensor Processing Unit (TPU).
- TPUs are designed to accelerate machine learning workloads and increase computing speed more than 200 times by tailoring architecture to meet the computation needs of a specific domain, such as matrix multiplication and machine learning.
- Cloud TPUs have been integrated across Google products and services to provide state-of-the-art hardware and supercomputing technology.

### Storage

- Compute and storage are decoupled for proper scaling capabilities in cloud computing.
- Google Cloud offers fully managed database and storage services, including Cloud Storage, Cloud Bigtable, Cloud SQL, Cloud Spanner, Firestore, and BigQuery.
- Choosing the right option to store and process data depends on the data type and business need.
- Unstructured data is information stored in a non-tabular form and is usually suited to cloud storage. Structured data represents information stored in tables, rows, and columns.
- Cloud Storage is a managed service for storing unstructured data. It has four primary storage classes: standard, nearline, cold line, and archive storage.
- Transactional workloads require standardized queries and fast data inserts and updates to maintain a system snapshot. Analytical workloads require complex queries and involve reading entire data sets.
- Cloud SQL and Cloud Spanner are options for transactional workloads that need to be accessed using SQL. Firestore is a transactional NoSQL document-oriented database that can be accessed without SQL.
- BigQuery is the best option for analytical workloads that require SQL commands and the analysis of petabyte-scale data sets.
- Cloud Bigtable provides a scalable NoSQL solution for analytical workloads that require real-time high-throughput applications with millisecond latency.

### The history of big data and ML products

- Google faced challenges related to big data early on due to large, fast-changing, and varied data sets.
- In 2002, Google released the Google file system (GFS), designed to handle data sharing and petabyte storage at scale.
- In 2004, Google introduced MapReduce, a new style of data processing designed to manage large-scale data processing across big clusters of commodity servers.
- In 2005, Google released Cloud Bigtable, a high-performance NoSQL database service for large analytical and operational workloads.
- In 2008, Dremel was introduced, which took a new approach to big data processing by breaking the data into smaller chunks called shards and then compressing them.
- In 2010, Google released Colossus, a cluster-level file system and successor to the Google file system, as well as BigQuery, a fully managed serverless data warehouse with built-in machine learning capabilities.
- In 2012, Spanner was released, which is a globally available and scalable relational database.
- In 2015, Google released TensorFlow, a free and open-source software library for machine learning and artificial intelligence, as well as Pub/Sub, a service used for streaming analytics and data integration pipelines to ingest and distribute data.
- In 2018, Google released the Tensor Processing Unit (TPU) and AutoML, a suite of machine learning products.
- In 2021, Google released Vertex AI, a unified ML platform.
- These products and services are made available through Google Cloud and include cloud storage, Dataproc, Cloud Bigtable, BigQuery, Dataflow, Firestore, Pub/Sub, Looker, Cloud Spanner, AutoML, and Vertex AI.

### Big data and ML product categories

- Google offers a range of big data and machine learning products
- Products can be divided into four general categories:
- Ingestion and process (digesting real-time and batch data)
	- Includes Pub/Sub, Dataflow, Dataproc, and Cloud Data Fusion
- Data storage
    - Includes Cloud Storage, Cloud SQL, Cloud Spanner, Cloud Bigtable, and Firestore
- Analytics
    - The major tool is BigQuery, which can be used to analyze data through SQL commands
    - Also includes Google Data Studio and Looker for data visualization
- Machine learning (ML)
⁃	ML products include both the ML development platform and AI solutions
    - The primary product of the ML development platform is Vertex AI, which includes AutoML, Vertex AI Workbench, and TensorFlow
    - AI solutions include Document AI, Contact Center AI, Retail Product Discovery, and Healthcare Data Engine
    - These products can help businesses unlock insights that only large amounts of data can provide.

### Customer example Gojek

- Gojek is a unicorn start-up company based in Jakarta, Indonesia, that offers motorcycle taxis (known as ojek), ride-hailing, food delivery, and grocery shopping services.
- Gojek started as a call center for ojek bookings in 2010 and launched its mobile application in 2015, which led to hyper-growth very quickly.
- Gojek has collected customer data since its inception and has relied heavily on technology and selecting the right technologies to grow and expand into new markets.
- Gojek chose Google Cloud to run its applications and data.
- One of Gojek's main goals is to match the right driver with the right request as quickly as possible.
- Gojek faced challenges with data latency and determining which location had too many or too few drivers to meet demand.
- To solve the data latency challenge, Gojek migrated its data pipelines to Google Cloud and used dataflow for streaming data processing and BigQuery for real-time business insights.
- To solve the challenge of determining driver locations, Gojek used data flow to build a streaming event data pipeline that allowed driver locations to ping Pub/Sub every 30 seconds and used data flow to process the data.
- The pipeline aggregated supply pings from drivers against booking requests and connected to Gojek's notification system to alert drivers of the best locations to go to.
- Gojek was able to visualize and identify supply and demand issues using Google Cloud's big data and machine learning products.
- Gojek has been able to actively monitor requests to ensure that drivers are in the areas with the highest demand, which brings faster bookings for riders and more work for drivers.

### Getting Started with Google Cloud Platform and Qwiklabs

- Log into Coursera using an incognito window to avoid using your personal Google account by mistake and incurring unexpected charges.
- Go to the lab activity page of the course.
- Accept the honor code and enter your name if prompted.
- Click "Open Tool" to open the lab in a new tab.
- Click "Start lab" and wait for the connection details to be displayed on the left.
- Click "Open Google Console" and sign in with the username and password provided in the connection details page.
- Quicklabs will create a new account for you each time you launch a lab, so you need to click through the initial account setup windows.
- Verify that you're using the right project by checking the current project ID displayed on the top left corner of the Google Console. Some labs have multiple project IDs and users.
- Some labs track your progress within the Quicklabs provided Google Cloud project, and you can view your score and the individual steps to be scored by clicking on the score displayed on the top right corner of the Quicklabs window.
- Once you've completed the lab, click "End lab" and confirm with "OK". You can also give feedback at this point.
- The Quicklabs provided project and any resources within that project will be deleted once you end the lab.
- You can check your lab completion status on the lab page or in the grades section of the course.

> Remember to use the Quicklabs provider credentials to sign into the cloud console, launch Coursera in an incognito window, and enjoy the rest of the course!

### Lab introduction Exploring a BigQuery Public Dataset

- Take a break from course videos and practice with BigQuery in the lab.
- In the lab, you will explore a public dataset, query it, create a custom table, load data into it, and query the table.
- Note that this exercise involves leaving the current learning platform and opening Quick Labs.
- Quick Labs offers a clean Google Cloud environment for a fixed period of time.
- You will have multiple attempts at each lab, so if you don't complete it the first time or want to experiment more with it later, you can return and start a new instance.

### Summary

- The first section of the course on big data and machine learning fundamentals has ended.
- Google Cloud infrastructure is divided into three layers: networking and security, compute and storage, and big data and machine learning products.
- Networking and security form the base layer, while compute and storage are in the middle.
- Compute and storage are decoupled in Google Cloud to scale independently based on demand.
- The top layer consists of big data and machine learning products.
- In the next section, the history of big data and machine learning technologies was discussed, and the four major product categories were explored: ingestion and process, storage, analytics, and machine learning.
- The case of gojek, an Indonesian on-demand multi-service platform, and digital payment technology group leveraging Google Cloud big data and machine learning products to expand their business was presented.
- Finally, Hands-On practice was provided with bigquery by analyzing a public data set.

## Data Engineering for Streaming Data

### Introduction of Data Engineering for streaming data

- Google Cloud infrastructure has layers, including big data and machine learning products.
- This section explores data engineering for streaming data with Google Cloud products and services.
- Ingest streaming data with Pub/Sub, process it with Dataflow, and visualize it with Data Studio or Looker.
- Data is saved and analyzed in a data warehouse such as BigQuery.
- Big Data challenges are examined, message-oriented architecture is learned, and streaming pipelines are designed and implemented with Apache Beam and Dataflow.
- Data insights are visualized on a dashboard with Looker and Data Studio.
- An end-to-end data pipeline that handles real-time data ingestion with Pub/Sub, processing with Dataflow, and visualization with Data Studio is built.
- Streaming data is a flow of data records generated by various data sources, analyzed in near real-time.
- Batch processing happens on stored data, while streaming data processing analyzes data as it flows through a system.
- Streaming data processing means data is analyzed in near real-time and actions are taken quickly.
- Streaming data is important for fraud and intrusion detection.
- Modern data processing has progressed toward working with real-time data streams.

### Big Data Challenges

The video discusses the four major challenges faced by data engineers and data scientists known as The Four Vs:

* Variety: Data comes in different formats and from various sources.
* Volume: Data can range from gigabytes to petabytes, which requires scalable pipeline code and infrastructure.
* Velocity: Data needs to be processed in near real-time as it reaches the system.
* Veracity: Data quality may be compromised due to inconsistencies and uncertainties from different data types and sources.

The challenges highlighted are common considerations for pipeline developers, and the section aims to provide better understanding of available tools to build a streaming data pipeline and avoid these challenges.

### Message oriented architecture

- Data ingestion is the first stage in a data pipeline where large amounts of streaming data are received.
- Data can come from many different devices and methods, making it challenging to distribute event messages to the right subscribers and ensure reliable, secure, and performant services.
- Pub/Sub is a distributed messaging service by Google Cloud that can handle distributed message-oriented architectures at scale.
- Pub/Sub receives messages from various device streams, ensures at least once delivery, and offers open APIs, global service, and end-to-end encryption.
- Pub/Sub uses a topic as a central element, allowing for decoupling of publishers and subscribers and enabling lightly coupled architectures with many different publishers and subscribers.
- Pub/Sub supports many different inputs and outputs, and messages can be reliably sent to a data warehouse through an elastic streaming pipeline.

### Designing streaming pipelines with Apache Beam

- Apache Beam is a popular solution for designing streaming pipelines.
- Dataflow creates a pipeline to process both streaming and batch data, allowing for ETL (Extract, Transform, Load) of data into a data warehouse for analysis.
- When designing a pipeline, data engineers should consider if the pipeline code will be compatible with both batch and streaming data, if there are existing templates or solutions that can be referenced, and if the SDK being used can handle late data and mid-flight aggregations and windowing.
- Apache Beam is a unified, portable, and extensible open source programming model for defining and executing data processing pipelines, including ETL, batch, and stream processing.
- Apache Beam provides pipeline templates and allows for writing pipelines in Java, Python, or Go.
- The Apache Beam SDK is a collection of software development tools that provide libraries for transformations and data connectors to sources and syncs.
- Apache Beam creates a model representation from your code that's portable across many runners, with Dataflow being a popular choice.

### Implementing streaming pipelines on Cloud Dataflow

- Apache Beam can create data processing pipelines
- Need an execution engine to implement these pipelines
- Consider questions when choosing an execution engine, such as maintenance overhead and pipeline scaling
- Dataflow is a fully managed service for executing Apache Beam pipelines in the Google Cloud ecosystem
- Dataflow handles infrastructure setup and maintenance, and is built on Google's infrastructure
- Dataflow allows for reliable auto-scaling to meet data pipeline demands
- Dataflow is serverless and noOps, meaning no operations team is required to manage it
- Dataflow optimizes the pipeline execution graph, schedules distributed work, auto-heals worker faults, and automatically rebalances efforts
- Data can be outputted to BigQuery or other options
- Dataflow templates cover common use cases across Google Cloud products, with three categories: streaming, batch, and utility templates

### Visualization with Looker

- A dashboard can be critical for data pipeline success
- Looker and Google Data Studio are two Google Cloud solutions
- Looker supports BigQuery and over 60 SQL databases
- Looker allows developers to define a semantic modeling layer on top of databases using LookML
- Looker is 100% web-based and has an API to embed reports in other applications
- Looker dashboards can visualize data, including multiple data visualization options
- Dashboards can be shared through Google Drive, Slack, and Dropbox
- Looker can plot data on a map to see distribution, busy areas, and peak hours
- Looker's features help draw insights to make business decisions
- For more training, refer to cloud.google.com/training

### Visualization with Data Studio

- Google offers Data Studio, a popular data visualization tool.
- Data Studio is integrated into BigQuery, making data visualization possible with just a few clicks.
- Looker, another data visualization tool, requires support from an administrator to establish a data connection.
- Data Studio is widely used across many Google products and applications, such as Google Analytics.
- Data Studio integrates with the Google Cloud billing dashboard.
- To create a Data Studio dashboard, there are three steps: 
  - choose a template (pre-built or blank report)
  - link the dashboard to a data source (BigQuery, local file, Google Sheets, Google Analytics, or a combination)
  - explore the dashboard.

### Lab introduction Creating a streaming data pipeline for a Real Time dashboard with Dataflow

- In the lab, you will build a streaming data pipeline to monitor sensor data and visualize it through a dashboard
- You will create a data flow job from a pre-existing template and subscribe to a pub subtopic streaming
- You will monitor a data flow pipeline into BigQuery and analyze results with SQL
- You will visualize key metrics in Data Studio
- SQL commands will be used in the lab, but strong SQL knowledge is not required
- BigQuery will be explored in more detail later in the course
- Multiple attempts are allowed for the lab

### Summary of Second section

Here's the summary in bullet points markdown format:

- Recap of the second section on building a data pipeline for streaming data
- Explored the four common Big Data challenges: volume, variety, velocity, and veracity
- Streaming data workflow provided by Google can help address these challenges
- Started with Pub/Sub for ingesting large volumes of IoT data from diverse resources in various formats
- Explored Dataflow, a serverless NoOps service to process the data (ETL)
- Introduced to two Google visualization tools: Looker and Data Studio.

## Big Data with BigQuery

### Introduction

- Introduction to BigQuery and its main services: storage and analytics
- BigQuery ML provides data to AI lifecycle within one platform
- BigQuery is a fully managed data warehouse, with structured and organized data used for advanced querying
- Differences between a data warehouse and a data lake
- BigQuery is a fully managed serverless solution with built-in features like machine learning, geospatial analysis, and business intelligence
- Pay-as-you-go pricing model for the number of bytes of data queried or permanent table storage, or Flat Rate pricing for a reserved amount of resources
- Data in BigQuery is encrypted at rest by default
- Built-in machine learning features to write ML models directly in BigQuery using SQL or export datasets to Vertex AI
- Typical data warehouse solution architecture with input data being real-time or batch data, processed through Pub/Sub and Dataflow, and linked through BigQuery for data access and analytics tools
- BigQuery outputs feed into two buckets: business intelligence tools and AI/ML tools, including visualization tools, Google Sheets, automl, and workbench
- BigQuery serves as a common staging area for data analytics workloads, granting access to business analysts, data scientists, and machine learning engineers.

### Storage and analytics

- BigQuery provides both storage and SQL-based analytics services.
- The services are connected by Google's high-speed internal network that allows for independent scaling of storage and compute based on demand.
- BigQuery can ingest data from various sources, including internal, external, multi-cloud, and public data sets.
- After the data is stored, it's fully managed, automatically replicated, backed up, and set to auto scale.
- BigQuery can query external data sources like data stored in other Google Cloud Storage services or database services.
- Three basic patterns to load data into BigQuery are batch load, streaming, and generated data.
- BigQuery is optimized for running analytical queries over large data sets, can perform queries on terabytes of data in seconds and petabytes in minutes.
- BigQuery supports ad hoc analysis using standard SQL, geospatial analytics, building machine learning models using BigQuery ML, and building Rich interactive business intelligence dashboards using BigQuery BI engine.
- BigQuery runs interactive queries by default, but also offers batch queries.
- BigQuery has a slightly different user interface that may be noticed during a demonstration.

### BigQuery demo - San Francisco bike share

- The transcript is about exploring a public dataset for San Francisco Bike Share trips on Google BigQuery.
- SQL or structured query language skills are necessary to explore the dataset.
- Tips are given to navigate the BigQuery public data sets, such as using backticks for hyphens in project names and highlighting data sets with the command key.
- The schema of the San Francisco Bike Share dataset is shown, including the trip ID, duration, start time, station, and geographic data.
- Querying the dataset is demonstrated, including selecting columns and using aggregate functions such as counting the number of trips by station name.
- Grouping by station name is necessary when using aggregate functions, and the resulting table shows the total number of trips for each station.

### Introduction to BigQuery ML

- BigQuery has evolved to support the data to AI lifecycle, including building ML models.
- ML model building and training can be time-consuming, requiring data export, transformation, feature engineering, and model building and training.
- BigQuery ML allows creating and executing ML models on structured datasets using SQL queries in two steps: creating a model and writing a prediction query.
- Hyperparameters can be manually controlled or handed over to BigQuery, and BigQuery ML supports supervised and unsupervised models.
- Classification and regression models are recommended for beginners, with options to benchmark against more complex models like DNN.
- BigQuery ML also supports ML Ops to deploy, monitor, and manage ML production, including importing/exporting models and parameter tuning using Vertex AI Vizier.

### Using BigQuery ML to predict customer lifetime value

- The goal is to predict customer lifetime value (LTV) with a machine learning model.
- LTV is a common metric used to estimate how much revenue or profit you can expect from a customer given their history and customers with similar patterns.
- A Google analytics eCommerce data set from Google's own merchandise store will be used in this example.
- Fields that may be useful in determining high-value customers include customer lifetime, page views, total visits, average time spent on the site, total revenue brought in, and e-commerce transactions on the site.
- Columns of data are fed into the model and the model figures out the relationship to best predict the label.
- A record or row in the data set is called an example, observation, or instance.
- A label is a correct answer that comes from historical data, which is used to train the model to predict future data.
- Labels can be either numeric (requires a linear regression model) or categorical (requires a logistic regression model).
- Data columns in the data table are called features or potential features, and each column of data is like a cooking ingredient that can be used in the model.
- Feature engineering is the process of sifting through data, understanding the quality of each column of data, and working with teams to get the most features or more history.
- BigQuery ML automatically performs one-hot encoding and splits the data set into training data and evaluation data.
- Once the model is trained and its performance is satisfactory, it can be used to predict future data sets.

### BigQuery ML Project Phases

- **Phase One:** 
  - Extract, transform, and load data into BigQuery, if not already present. 
  - Use easy connectors to get data from other Google products like YouTube.
  - Enrich existing data warehouse with other data sources using SQL joins.

- **Phase Two:**
  - Select and pre-process features. 
  - Use SQL to create the training data set for the model to learn from.
  - BigQuery ML does some pre-processing, like one-hot encoding of categorical variables.

- **Phase Three:**
  - Create the model inside BigQuery using the `CREATE MODEL` command.
  - Specify model type and pass a SQL query with training data set.

- **Phase Four:**
  - Execute `ml.evaluate` query to evaluate model performance on evaluation data set.
  - Analyze loss metrics like root mean squared error for forecasting models and area under the curve accuracy, precision, and recall for classification models.

- **Phase Five:**
  - Use the trained model to make predictions using `ml.predict` command.
  - Results will have the predicted label field added to the field name.

### BigQuery ML key commands

Here are the key commands of BigQuery ML summarized in bullet points:

- To create a model, use the `CREATE MODEL` command.
- To overwrite an existing model, use the `CREATE OR REPLACE MODEL` command.
- Models have options, and the only required one is the model type.
- Use the `ML.WEIGHTS` command to inspect what the model learned, with the output being a numerical value indicating how important each feature is for predicting the label.
- Use the `ML.EVALUATE` command to evaluate the model's performance.
- To make batch predictions, use the `ML.PREDICT` command on a trained model and pass through the data set.
- In BigQuery ML, you need a field in your training data set titled "label" or specify which field(s) your labels are using as the input label columns in your model options.
- Your model features are the data columns that are part of your select statement after your `CREATE MODEL` statement.
- Use the `ML.FEATURE INFO` command to get statistics and metrics about the column for additional analysis after a model is trained.
- Model objects are stored in your BigQuery data set, and you can view information such as when it was last updated or how many training runs it completed.
- Creating a new model is as easy as writing `CREATE MODEL`, choosing a type, and passing in a training data set.
- Use linear regression for forecasting numeric fields and logistic regression for classification of discrete classes.
- Use `ML.TRAINING INFO` to view training progress while the model is running and even after it's complete.
- Use `ML.WEIGHTS` to inspect what the model learned about the importance of each feature.
- Use `ML.EVALUATE` to see how well the model performed against its evaluation data set.
- Use `ML.PREDICT` to get predictions, referencing your model name and prediction data set.

### Summary

Here's the summary in bullet points markdown format:

- BigQuery is a data warehouse that provides both storage and analytical services.
- BigQuery serves as a staging area for data between ingestion and processing, and outputs data to BI and ML tools.
- BigQuery offers machine learning features in addition to traditional data warehousing.
- BigQuery can be used to directly build ML models in five key phases:
  - Phase 1: Extract, transform, and load data into BigQuery.
  - Phase 2: Select and pre-process features using SQL to create the training dataset for the model.
  - Phase 3: Create the ML model inside BigQuery.
  - Phase 4: Evaluate the performance of the trained model on the evaluation dataset using an `ml.evaluate` query.
  - Phase 5: Use the trained model to make predictions when you're satisfied with its performance.

## Machine Learning Options

### Introduction

- Introduction to machine learning on Google Cloud
- Overview of Google's contributions to AI and machine learning
- Google recognized as a leader in cloud AI developer services
- Example of Google's AI technology: natural language processing used in Gmail's smart reply feature
- Goal of Google's AI technologies is to enable every company to be an AI company
- Potential solutions for various industries using AI and ML
- Encourages viewers to think about how AI and ML can help solve problems in their business.

### Options to build ML models

Here are the key points from the transcript:

- Google Cloud provides four options for building machine learning (ML) models.
- The options are: 
  - BigQuery ML, which uses SQL queries to create and execute ML models in BigQuery for tabular data.
  - Pre-built APIs, which allow you to use existing ML models created by Google without building your own models.
  - AutoML, which is a no-code solution for building your own ML models on Vertex AI through a point-and-click interface for tabular, image, text, and video data.
  - Custom Training, which allows you to code your own ML environment for full control over the ML pipeline for tabular, image, text, and video data.
- The best option for building an ML model will depend on your business needs and ML expertise.
- Key factors to consider when choosing an option are data type, training data size, ML and coding expertise required, flexibility to tune hyperparameters, and time to train the model.
- BigQuery ML is suitable if you are familiar with SQL and have tabular data in BigQuery.
- Pre-built APIs are user-friendly and require no ML expertise, making them a good choice for business users or developers with little ML experience.
- AutoML is a good choice if you want to build custom models with your own training data while spending minimal time coding.
- Custom Training provides full control of the ML workflow for ML engineers and data scientists.

### Pre built APIs

- Pre-built APIs are offered as services and can save time and effort in building, curating, and training data sets for machine learning models.
- Good machine learning models require high-quality training data, typically hundreds of thousands of records, to train a custom model.
- Pre-built APIs can serve as building blocks for creating an application without the expense or complexity of creating custom models.
- Some pre-built APIs include speech-to-text, natural language processing, translation, text-to-speech, vision, and video intelligence.
- Google has already trained these models using their own data sets, meaning less work for the user.
- The vision API can be tried out in a browser by navigating to cloud.google.com/vision in Chrome and uploading an image.
- To build a production model, a JSON object request must be passed to the API and the response must be parsed.

### AutoML

#### Introduction
- AutoML stands for Automated Machine Learning.
- AutoML was built to automate the process of training and deploying ML models to save time and effort.

#### Technologies
- Transfer Learning: builds a knowledge base in the field by taking advantage of pre-trained models that have been trained on similar larger data sets.
- Neural Architecture Search: finds the optimal model for the relevant project.

#### Benefits
- No code solution that trains high-quality custom machine learning models with minimal effort and requires little machine learning expertise.
- Allows data scientists to focus on tasks like defining business problems or evaluating and improving model results.
- Useful as a tool to quickly prototype models and explore new data sets before investing in development.

#### Working of AutoML
- AutoML supports four types of data: image, tabular, text, and video.
- For each data type, AutoML solves different types of problems called objectives.
- Pre-built APIs use pre-built machine learning models but AutoML uses custom-built models.
- AutoML allows users to train their own machine learning models using their own data.
- For each data type, AutoML has different models like classification, regression, forecasting, entity extraction, sentiment analysis, object tracking, and action recognition.

#### Conclusion
- AutoML is a powerful tool that can help across different data types and objectives.

### Custom Training

* Google Cloud offers several options for building machine learning models:
  * BigQuery ML pre-built APIs
  * AutoML
  * Custom Training
* Custom Training allows you to code your own machine learning model using Vertex AI Workbench.
* Workbench is a single development environment for the entire data science workflow, including exploring, training, and deploying a machine learning model with code.
* Before coding, you must decide on the environment for your ML training code:
  * Pre-built container: a fully furnished kitchen with cabinets and appliances representing dependencies and cookware representing libraries needed for your ML training. This is best if your training needs a platform like TensorFlow, PyTorch, scikit-learn, or XGBoost, and Python code.
  * Custom container: an empty room where you define the exact tools you need to complete the job.

### Vertex AI

- Google has invested in developing big data and AI for years
- Google has applied AI technologies to many of its products and services
- Challenges in developing and deploying machine learning models include handling large data, selecting the right model, and managing production
- Only half of Enterprise ml projects get past a pilot phase
- Google's solution to these challenges is Vertex AI, a unified platform for creating, deploying, and managing models at scale
- Vertex AI offers a seamless user experience from data preparation to production
- It is scalable and can automatically scale storage and computing power
- It is sustainable as all artifacts and features created can be reused and shared
- It is speedy and produces models with 80% fewer lines of code than competitors
- Vertex AI offers two options for building models: AutoML (codeless) and custom training (code-based)

### AI Solutions

- Google Cloud offers an AI solution portfolio with three layers:
  - AI foundation (Google Cloud infrastructure and data)
  - AI development platform (including AutoML, Custom Training, pre-built APIs, and BigQuery ML)
  - AI solutions (divided into horizontal and vertical solutions)
- Horizontal solutions can be applied to any industry and include:
  - Document AI (uses computer vision, OCR, and NLP to extract information from documents)
  - Contact Center AI (improves customer service through AI automation and assistance)
- Vertical solutions are industry-specific and include:
  - Retail product discovery (provides Google-quality search and recommendations for retailers)
  - Google Cloud Healthcare Data Engine (generates Healthcare insights and analytics)
  - Lending Doc AI (automates mortgage document processing for borrowers and lenders)
- More information on Google Cloud's AI solutions can be found at cloud.google.com/Solutions/AI

### Summary

- Recap of Google's AI offerings in Google Cloud
- Four options for building machine learning models: 
  - BigQuery ML (SQL-based models)
  - Pre-built APIs (ready-to-use without ML expertise)
  - AutoML (codeless custom model building)
  - Custom Training (full control of ML workflow with code)
- Introduction of Vertex AI, which combines AutoML and Custom Training for production and ease of use
- Choosing the best option depends on business needs and ML expertise
- Pre-built APIs for common perceptual tasks (Vision, Video, Natural Language)
- AutoML for custom models with minimal coding
- Custom Training for full control of ML workflow with code on Vertex Workbench
- Google Cloud AI Solutions built on top of the four ML development options to meet horizontal and vertical market needs

## The Machine Learning Workflow with Vertex AI

### Introduction

- The focus of this section is on the machine learning workflow with Vertex AI, Google's AI platform, from data preparation to model deployment.
- The process of building a custom ML model is similar to serving food in a restaurant, starting with preparing raw ingredients to serving dishes to a table.
- Machine learning is different from traditional programming where data plus rules (algorithms) lead to answers.
- Machine learning involves feeding a machine a large amount of data along with answers to conclude from the data, allowing the machine to learn and solve puzzles on its own.
- Cloud storage and computing are essential for successful machine learning.
- Three key stages of the learning process are data preparation, model training, and model serving, which are iterative.
- Data used in machine learning can either be structured (numbers and text saved in tables) or unstructured (data that can't be put into tables like images and videos).
- Vertex AI provides two options to build ML models: AutoML (codeless solution) and Custom Training (code-based solution).
- Vertex AI provides many features to support the ML workflow, including Feature Store, Vizier, Explainable AI, and Pipelines.

### Data Preparation

- The first stage of an automl workflow is data preparation, which involves uploading data and preparing it for model training with feature engineering.
- When uploading a data set in the Vertex AI user interface, you need to provide a name, select the data type, and objective.
- Automl allows four types of data: image, tabular, text, and video.
- Labels need to be added to the data to provide a training target. A label can be manually added or added by using Google's paid label service.
- After uploading data to automl, the next step is preparing the data for model training with feature engineering, which is like processing ingredients before cooking.
- Feature engineering involves preparing features, which are factors that contribute to the prediction. Vertex AI has a feature store to centralize and organize machine learning features.
- The benefits of using Vertex AI feature store include shareable features, reusable features, scalable features, and an easy-to-use interface.

### Model Training

- Model training is like cooking a recipe, where data is the ingredients.
- Model training involves two steps: model training and model evaluation.
- Artificial Intelligence (AI) is an umbrella term that includes computers mimicking human intelligence, while machine learning is a subset of AI that mainly refers to supervised and unsupervised learning.
- Supervised learning is task-driven and identifies a goal, while unsupervised learning is data-driven and identifies a pattern.
- Classification and regression are major types of supervised learning, while clustering, association, and dimensionality reduction are major types of unsupervised learning.
- Google Cloud provides four machine learning options, including AutoML and pre-built APIs, where the best model is selected to meet the business goal automatically.
- With BigQuery ML and custom training, hyperparameters need to be specified, which are user-defined knobs that help guide the machine learning process.
- AutoML automatically adjusts hyperparameters using a neural architect search that finds the best-fit model by comparing the performance against thousands of other models.

### Model Evaluation

- Model evaluation is a crucial step in model training to ensure that it meets expectations.
- Vertex AI provides comprehensive evaluation metrics for model performance, which includes two sets of measurements based on the confusion matrix and feature importance.
- A confusion matrix is a table that measures the predicted and actual values of a classification problem, consisting of true positive, true negative, false positive, and false negative combinations.
- Recall and precision are two popular metrics used to evaluate model performance, with recall measuring how many positive cases were predicted correctly and precision measuring how many predicted positive cases were actually positive.
- Precision and recall often involve a trade-off, depending on the use case and the goal of the model.
- Vertex AI platform visualizes the Precision and Recall curve to optimize for the required metric.
- Feature importance is displayed through a bar chart to determine the contribution of each feature in a prediction, which helps in feature selection for the model.
- Vertex AI's comprehensive machine learning functionality is called explainable AI, which includes a set of tools and frameworks to interpret the predictions made by machine learning models.

### Model Deployment and Monitoring

- Model serving is the final stage of the machine learning workflow, consisting of model deployment and model monitoring.
- Model management exists throughout the workflow to manage the underlying machine learning infrastructure.
- ML apps combine machine learning development with operations, applying DevOps principles to machine learning models to solve production challenges.
- ML apps advocates for automation and monitoring at each step of the ML system construction, enabling continuous integration, training, and delivery.
- Model deployment options include deploying to an endpoint for immediate results with low latency, batch prediction for accumulated data processing, and offline prediction for specific environments.
- Model monitoring is critical in ML ops and is facilitated by Vertex AI Pipelines, which automates, monitors, and governs ML systems by orchestrating workflows in a serverless manner.
- With Vertex AI Workbench, users can define their own pipelines using pre-built pipeline components.
- The combination of model deployment and monitoring completes the exploration of the machine learning workflow, ensuring smooth operation of the ML system.

### Lab introduction: Predicting loan risk with AutoML

In this lab, you will:
- Use AutoML, a codeless tool, to build a machine learning model to predict loan risk.
- Work with a dataset from a financial institution that contains 2050 data points.
- Note that AutoML requires at least 1,000 data points in a dataset.
- Practice the three phases of the machine learning workflow: data preparation, model training, and model serving.

### Lab recap Predicting loan risk with AutoML

- Lab used AutoML to build a machine learning model without writing any code
- Confusion matrix was used to evaluate the model's performance
- True positives were 100%, true negatives were 87%, false negatives were 0%, and false positives were 13%
- Having high true positives and true negatives and low false positives and false negatives is generally good, but it depends on business goals
- Model performance can be improved by using more accurate data, a larger dataset, a different ML model, or tuning hyperparameters
- Precision-recall curve shows how the model counts positive cases based on the confidence threshold
- Higher threshold increases precision but decreases recall, lower threshold decreases precision but increases recall
- Setting threshold to 0 produces highest recall of 100% and lowest precision of 50%
- Setting threshold to 1 produces highest precision of 100% and lowest recall of 1%
- Setting inappropriate thresholds can lead to high business risk and loss

### Summary

- Three stages of machine learning workflow:
  1. Data preparation
     - Upload data and apply feature engineering
     - Gathering ingredients and chopping/prepping in the kitchen
  2. Model training
     - Train and evaluate the model
     - Experiment with recipes and taste the meal
  3. Model serving
     - Deploy and monitor the model
     - Serve the meal to customers and adjust menu

## Course Summary

- Congrats on completing the Big Data and Machine Learning Fundamentals course!
- The course introduced several products and technologies to support Google's data-to-AI lifecycle.
- The course was divided into four sections.
- In Section 1, you learned about Google Cloud infrastructure and Google's big data and machine learning products, including the middle and top layers of the infrastructure.
- In Section 2, you explored data engineering for streaming data, including building a streaming data pipeline from ingestion with Pub/Sub to visualization using Data Studio and Looker.
- In Section 3, you learned about BigQuery, Google's fully managed data warehouse, and BigQuery ML, the machine learning tool used for developing machine learning models directly in BigQuery.
- In Section 4, you explored options for building and deploying machine learning models with Google Cloud, including BigQuery ML, pre-built APIs, AutoML, and Vertex AI Custom Training.
- In the final section, you learned about the machine learning workflow using Vertex AI, a unified platform that brings all the components of the machine learning ecosystem and workflow together.
- For more training and hands-on practice with data engineering and analytics, refer to cloud.google.com/training/data-engineering-and-analytics.
- For more training with machine learning and AI, explore the options available at cloud.google.com/training/machine-learning-ai.
- Consider working toward a Google Cloud certification to validate your expertise and showcase your ability to transform businesses with Google Cloud technology. Learn more at cloud.google.com/certifications.