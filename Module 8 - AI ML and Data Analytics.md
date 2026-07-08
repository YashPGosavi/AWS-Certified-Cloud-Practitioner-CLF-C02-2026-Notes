# Module 8 - AI ML and Data Analytics

## Introduction to AI and Machine Learning

- **AI** is the broader field of creating systems that can perform human-like tasks.
- **Machine learning (ML)** is a type of AI where systems learn patterns from historical data instead of following explicit rules.
- ML models use those patterns to make predictions or decisions on new data.

- **Key takeaway**: AI is the umbrella term, and ML is one way to build AI systems.


---


## AI/ML on AWS

- AWS offers AI/ML solutions for common business use cases such as:
  - predicting trends
  - routing decisions
  - anomaly detection
  - recommendations
- A common example is the Amazon.com recommendations engine.

### AWS AI/ML stack

- **AI services**
   - Pre-built, fully managed services that are already trained for specific tasks.

- **ML services**
   - More customizable services where you build, train, and deploy your own models.
   - The main service here is **Amazon SageMaker AI**.

- **ML frameworks and infrastructure**
   - The most custom option for experienced ML teams.
   - Uses ML frameworks and AWS infrastructure to build solutions from the ground up.


---


## AWS AI/ML Solutions

- The AWS AI/ML stack can be thought of as a progression from easy-to-use pre-built services to highly customized ML environments.


### Tier 1: Pre-built AWS AI services

- These services are already trained and ready to use.
- They help you solve common problems without building models from scratch.


#### Language services

1. **Amazon Comprehend**
   - Uses natural language processing to extract insights from text.
   - Common use cases:
     - content classification
     - sentiment analysis
     - compliance monitoring

2. **Amazon Polly**
   - Converts text into lifelike speech.
   - Common use cases:
     - virtual assistants
     - e-learning
     - accessibility support

3. **Amazon Transcribe**
   - Converts speech into text.
   - Common use cases:
     - call transcription
     - subtitling
     - media metadata generation

4. **Amazon Translate**
   - Translates text across multiple languages.
   - Common use cases:
     - document translation
     - multilingual applications


#### Computer vision and search services

1. **Amazon Kendra**
   - Search service that understands context and returns more relevant answers than keyword search.
   - Common use cases:
     - intelligent search
     - chatbots
     - application search

2. **Amazon Rekognition**
   - Analyzes images and videos to identify objects, people, text, scenes, and activities.
   - Common use cases:
     - content moderation
     - identity verification
     - media analysis

3. **Amazon Textract**
   - Extracts text, forms, and tables from documents.
   - Common use cases:
     - financial forms
     - healthcare forms
     - government document processing


#### Conversational AI and personalization services

1. **Amazon Lex**
   - Adds voice and text conversational interfaces to applications.
   - Common use cases:
     - virtual assistants
     - FAQ bots
     - automated application bots

2. **Amazon Personalize**
   - Uses historical data to generate personalized recommendations.
   - Common use cases:
     - streaming recommendations
     - product recommendations
     - trending recommendations


### Tier 2: ML services

- This tier gives you more control than pre-built AI services, without requiring you to manage infrastructure.

#### Amazon SageMaker AI

- Amazon SageMaker AI is a fully managed service for building, training, and deploying ML models.
- It provides tools for:
  - data exploration
  - model training
  - experiment tracking
  - debugging
  - monitoring
- It also provides access to pre-trained models that you can deploy quickly.

##### Key benefits of SageMaker AI

1. **Choice of ML tools**
   - Data scientists can use the IDE, while business users can use no-code options.

2. **Fully managed infrastructure**
   - AWS handles the infrastructure so teams can focus on model development.

3. **Repeatable ML workflows**
   - Helps standardize MLOps practices, governance, transparency, and auditability.


### Tier 3: ML frameworks and infrastructure

- This tier is for organizations that need complete control over the ML training process.
- It is the most custom and flexible option.

#### Core components

1. **ML frameworks**
   - Software libraries or tools used to build ML models.
   - Examples include:
     - PyTorch
     - Apache MXNet
     - TensorFlow

2. **AWS ML infrastructure**
   - Infrastructure used for advanced ML workloads.
   - Examples include:
     - ML-optimized Amazon EC2 instances
     - Amazon EMR
     - Amazon ECS


---


## Introduction to Generative AI on AWS

- **Deep learning** is a subset of ML that uses layers of artificial neurons to process information.
- **Generative AI** is a type of deep learning that uses very large ML models called **foundation models (FMs)**.
- Foundation models are pre-trained on large datasets and can be adapted to many tasks.
- **Large language models (LLMs)** are a popular type of foundation model.

- **Key takeaway**: traditional ML is often task-specific, while generative AI uses foundation models that can be adapted to multiple tasks.


### Generative AI on AWS

AWS offers these generative AI options:

1. **Amazon SageMaker JumpStart**
   - ML hub with pre-built models and solutions that can be deployed quickly.

2. **Amazon Bedrock**
   - Fully managed service for working with foundation models from Amazon and leading AI companies.

3. **Amazon Q**
   - Interactive AI assistant that connects to company knowledge and systems.


---


## AWS Generative AI Solutions

### Amazon SageMaker JumpStart

- SageMaker JumpStart is a machine learning hub within SageMaker AI.
- It provides pre-built solutions across areas like:
  - computer vision
  - NLP
  - tabular data
- These models can be fine-tuned and deployed with a few clicks.

#### Common use cases

1. **Rapid ML model deployments**
   - Quickly deploy pre-trained models without deep ML expertise.

2. **Custom fine-tuned solutions**
   - Fine-tune foundation models with your own domain data.

3. **ML experiments and prototypes**
   - Compare different models before committing to one approach.


### Amazon Bedrock

- Amazon Bedrock is a fully managed service for building generative AI applications with foundation models.
- It gives access to models from Amazon and leading AI companies through a single API.
- It supports experimentation, fine-tuning, and integration into AWS applications.

#### Common use cases

1. **Enterprise-grade generative AI**
   - Build production-ready apps with security, privacy, and scalability.

2. **Multimodal content generation**
   - Generate multiple content types such as text and images.

3. **Advanced conversational AI**
   - Build assistants that can connect to enterprise data.


### Amazon Q products

- Amazon Q is a generative AI assistant designed to help employees work faster and make decisions sooner.

1. **Amazon Q Business**
   - Answers questions and helps take actions using company knowledge and connected systems.
   - Common use cases:
     - information requests
     - automated workflows
     - insight extraction

2. **Amazon Q Developer**
   - Gives code recommendations and helps developers write code faster.
   - Common use cases:
     - code generation
     - reliability and security improvements
     - automated code reviews


---


## Introduction to Data Analytics

- AI/ML and data analytics both depend on clean, accessible data.
- **ETL** stands for:
  - **Extract**
  - **Transform**
  - **Load**
- Data pipelines make ETL repeatable and automated.

### Data analytics

- Data analytics is the process of transforming raw historical data into useful insights and trends.
- Common use cases include:
  - explaining lending decisions
  - analyzing clinical trial data
  - supporting regulatory transparency


---


## Data Pipelines on AWS

- AWS provides services for each stage of a data pipeline.

### Data ingestion

- Data ingestion moves data from source systems into storage.
- Use **real-time ingestion** when data is needed immediately.
- Use **batch ingestion** when some delay is acceptable.

1. **Amazon Kinesis Data Streams**
   - Real-time ingestion for applications, streams, and sensors.

2. **Amazon Data Firehose**
   - Near real-time, fully managed data delivery service.
   - Delivers data to data lakes, warehouses, and analytics services.

### Data storage

- Data is usually consolidated into one place for analysis.
- Common storage choices are:
  - **data lakes** for raw data
  - **data warehouses** for structured analytics

1. **Amazon S3**
   - Common choice for data lakes.
   - Stores structured or unstructured data at scale.

2. **Amazon Redshift**
   - Fully managed data warehouse for petabytes of structured or semi-structured data.

### Data cataloging

1. **AWS Glue Data Catalog**
   - Centralized metadata repository.
   - Improves data discovery and helps analytics services understand data sources.

### Data processing

1. **AWS Glue**
   - Fully managed ETL service for preparing and transforming data.

2. **Amazon EMR**
   - Managed big data processing service for large-scale analytics workloads.
   - Supports frameworks like:
     - Apache Spark
     - Apache Hadoop
     - Apache Hive

### Data analysis and visualization

1. **Amazon Athena**
   - Serverless SQL query service for analyzing data in S3 and other sources.

2. **Amazon Redshift**
   - Best for frequent, high-performance analytical queries on large datasets.

3. **Amazon QuickSight**
   - Dashboard and reporting service for technical and non-technical users.
   - Includes **Amazon Q in QuickSight** for natural language queries.

4. **Amazon OpenSearch Service**
   - Search and analytics service for logs, traces, metrics, and content discovery.

---

## Data Analytics and AI/ML

- A common AWS pattern is to use one data pipeline for both analytics and ML training.
- The flow is:
  1. capture application data
  2. ingest and transform it
  3. store it in S3
  4. catalog it with Glue
  5. analyze it with Athena
  6. train ML models with SageMaker AI

### Example workflow

1. **Make recommendations**
   - An e-commerce ML model generates product recommendations.

2. **Store app data**
   - Amazon DynamoDB stores historical customer data.

3. **Ingest data**
   - Kinesis Data Streams ingests the data, and Firehose aggregates it.

4. **Process data**
   - AWS Lambda transforms JSON into CSV.

5. **Deliver data**
   - Firehose sends the data to an Amazon S3 data lake.

6. **Catalog data**
   - AWS Glue Data Catalog describes the schema and location of the data.

7. **Perform data analytics**
   - Athena is used to query the data.

8. **Train model**
   - SageMaker AI reads the same data from S3 to train updated ML models.

### Common exam reminders

- AI is the broader field, ML is a subset of AI, and deep learning is a subset of ML.
- SageMaker AI is the main managed ML service on AWS.
- Bedrock is for building generative AI applications with foundation models.
- S3 is the most common storage layer for analytics and ML pipelines.
- Glue Data Catalog helps make data discoverable and usable across services.

---