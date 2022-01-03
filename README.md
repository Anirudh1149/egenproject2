# EL Pipeline using pub/sub, Dataflow, Big Query 
# PROJECT
This project uses and EL Pipeline that starts in pub/sub, goes through Dataflow, and ends up in a table in big query this show us that we can do continuous integration as many times as we like in a day and have all of them delivered.

# Architecture 

![image](https://user-images.githubusercontent.com/28685243/147947682-1527499a-792e-4378-ba7a-93958649d7be.png)

PUB/SUB: 

It’s a messaging system

Using Topics and subscription 

Pull and push methods 

DATA FLOW:

Hadoop cluster

Spark Runner (completely serverless)

Apache Bean (SDK to write pipelines and for templates that)

BIG QUERY:

Data warehouse 

Datasets and tables 

SQL languages for query

Terabytes analyzed in seconds

## PROJECT PROCESS:

Created a project anirudhegen1 to be our project with location as no organization. Enabled the API data flow Then opened pub/sub went into topics created a topic called sensor-data. Went into big query and created a dataset in the project as training. Then created an empty table with name senor data and added some field that I want.

![image](https://user-images.githubusercontent.com/28685243/147947702-fc40fd40-d574-4b72-af82-53843d9a3109.png)

Then went into dataflow created a job from template. For the pipeline to get in usage connected the pub/sub topic to big query which created a subscription, and in the subscription, I used pull operation cause I am not doing real-time. Then went into dataflow that was enabled before then created a job with the name movingsensordatatobigquery and for cloud data flow used the created pub/sub topic to big query, and the output table is the table sensor-data that was created earlier. For the temp storing the table I created a bucket with the name sensordatatobigquery. Once done with this set up a graph will be generated along with pub/sub subscription. Then for the final step I went into pub/sub topic and published message in publish message in JSON. Once it goes through the pipeline with no error, we can see output in the created sensor data table in the big query.
 
![image](https://user-images.githubusercontent.com/28685243/147947723-47750175-faae-424d-90f9-9725be32b812.png)

If there is any error, we will get a error file in the dataset training under the sensor data table with sensor data error. According to the error, we can make the changes with inputs that we are giving the pipeline.
 
![image](https://user-images.githubusercontent.com/28685243/147947736-18cb03a4-480f-4dff-a4b6-347eea53b24a.png)
