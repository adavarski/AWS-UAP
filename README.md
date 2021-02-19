## UAP : Universal Analytics Platform (AWS-based)


Universal Analytics Platform architecture with Snowflake DWH, EMR cluster, Kinesis Firehose, DynamoDB, RDS, etc.:

<img src="https://github.com/adavarski/AWS-UAP/blob/main/pictures/AWS-UAP-architecture.png" width="800">

Note1: Snowflake helped us to leverage big data and streaming capabilities that were impossible with the legacy solution. For big data, we were processing web logs for example within Apache Spark deployed on top of the EMR cluster. Snowflake accesses Parquet files, and we don’t need to load them into Snowflake. For the streaming use case, we leveraged DynamoDB streams and Kinesis Firehose, and all data is sent into an S3 bucket where Snowflake can consume it.

Note2: Near Real-Time data and analytics



### UAP provisioners
Contains the various provisioning projects used by the Universal Analytics Platform. See the relevant readme file of each project for more detail about each provisioner.
