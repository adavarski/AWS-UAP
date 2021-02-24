## WIP -> UAP : Universal Analytics Platform (AWS-based)


### 1.Universal Analytics Platform architecture with AWS EMR cluster, AWS Kinesis Firehose, Snowflake DWH, AWS DynamoDB, AWS RDS, AWS SageMaker, Matillion (Batch/ETL), etc.:

<img src="https://github.com/adavarski/AWS-UAP/blob/main/pictures/AWS-UAP-architecture.png" width="800">

Note1: Near Real-Time Data/Analytics Platform

Note2: Snowflake helped us to leverage big data and streaming capabilities that were impossible with the legacy solution. For big data, we were processing web logs for example within Apache Spark deployed on top of the EMR cluster. Snowflake accesses Parquet files, and we don’t need to load them into Snowflake. For the streaming use case, we leveraged DynamoDB streams and Kinesis Firehose, and all data is sent into an S3 bucket where Snowflake can consume it.

Note3: Objective for UAP (default UAP).

### 2.Universal Analytics Platform architecture with AWS Kinesis, AWS SNS/SQS, Redshift DWH, Apache Airflow (Batch/ETL), etc.:

<img src="https://github.com/adavarski/AWS-UAP/blob/main/pictures/2-UAP.png" width="800">

### 3.Universal Analytics Platform architecture with AWS Managed Kafka cluster (MSK), AWS EMR cluster, Apache Airflow (Batch/ETL), etc.:

<img src="https://github.com/adavarski/AWS-UAP/blob/main/pictures/3-UAP.png" width="800">

## WIP -> UAP provisioners
Contains the various provisioning projects used by the Universal Analytics Platform. See the relevant readme file of each project for more detail about each provisioner.

- uap-bastion-provisioner
  - Terraform modules for bastion/jumpbox VM.
  - Docker image, running Ansible & CloudFormation to provision and decommission bastion/jumpbox VM for UAP infrastructure.

- uap-dynamodb-provisioner
  - Terraform modules for AWS DynamoDB table used to store client inventory settings.
  - Docker image, running Ansible & CloudFormation to provision and decommission AWS DynamoDB table used to store client inventory settings.
  
- uap-rds-provisioner
  - Terraform modules for UAP AWS RDS stacks.
  - Docker image, running Ansible & CloudFormation to provision and decommission UAP AWS RDS stacks.

- uap-matillion-provisioner
  - Terraform modules for Matillion ETL VM.
  - Docker image, running Ansible & CloudFormation to provision and decommission Matillion ETL VM.

- uap-airflow-provisioner
  - Terraform modules for Apache Airflow ETL VM.
  - Docker image, running Ansible & CloudFormation to provision and decommission Apache Airflow ETL VM.

- uap-kinesis-provisioner
  - Terraform modules for Kinesis Firehose.
  - Docker image, running Ansible & CloudFormation to provision and decommission Kinesis Firehose.

- uap-sns-provisioner
  - Terraform modules for S3 bucket, SNS Topics.
  - Docker image, running Ansible & CloudFormation to spin up an S3 bucket, SNS Topic to be used as part of the event-driven publishing/analytics pipelines.

- uap-sqs-provisioner
  - Terraform modules for S3 bucket, SQS Queues.
  - Docker image, running Ansible & CloudFormation to spin up an S3 bucket, SQS Queues to be used as part of the event-driven publishing/analytics pipelines.

- uap-emr-provisioner
  - Terraform modules for AWS EMR cluster.
  - Docker image, running Ansible & CloudFormation to provision and decommission AWS EMR cluster.
  
- uap-databricks-provisioner
  - Terraform modules for Databricks cluster.  
  - Docker image, running Ansible & CloudFormation to provision and decommission Databricks cluster.

- uap-snowflake-provisioner
  - Terraform modules for AWS Snowflake DWHs.
  - Docker image, running Ansible & CloudFormation (or Terraform) to provision and decommission Snowflake DWHs.

- uap-redshift-provisioner
  - Terraform modules for AWS Redshift DWHs.
  - Docker image, running Ansible & CloudFormation (or Terraform) to provision and decommission AWS Redshift DWHs.

- uap-sagemaker-provisioner
  - Terraform modules for AWS SageMaker.
  - Docker image, running Ansible & CloudFormation to provision and decommission AWS SageMaker.

- uap-tableau-provisioner
  - Terraform modules for Tableau Server VM.
  - Docker image, running Ansible & CloudFormation to provision and decommission Tableau Server VM.

- uap-jenkins-provisioner
  - Terraform modules for Jenkins CI/CD @UAP infrastructure.
  - Docker image, running Ansible & CloudFormation to provision and decommission Jenkins CI/CD for UAP infrastructure.

- uap-elasticsearch-provisioner
  - Terraform modules for AWS Managed ElasticSearch clusters.
  - Docker image, running Ansible & CloudFormation to provision and decommission UAP AWS Managed ElasticSearch clusters.

- uap-msk-provisioner
  - Terraform modules for AWS Managed Kafka cluster (MSK).
  - Docker image, running Ansible & CloudFormation to provision and decommission AWS Managed Kafka cluster (MSK).





