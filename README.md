## UAP : Universal Analytics Platform (AWS-based)


Universal Analytics Platform architecture with Snowflake DWH, AWS EMR cluster, AWS Kinesis Firehose, AWS DynamoDB, AWS RDS, etc.:

<img src="https://github.com/adavarski/AWS-UAP/blob/main/pictures/AWS-UAP-architecture.png" width="800">

Note1: Near Real-Time Data and Analytics Platform

Note2: Snowflake helped us to leverage big data and streaming capabilities that were impossible with the legacy solution. For big data, we were processing web logs for example within Apache Spark deployed on top of the EMR cluster. Snowflake accesses Parquet files, and we don’t need to load them into Snowflake. For the streaming use case, we leveraged DynamoDB streams and Kinesis Firehose, and all data is sent into an S3 bucket where Snowflake can consume it.

### UAP provisioners
Contains the various provisioning projects used by the Universal Analytics Platform. See the relevant readme file of each project for more detail about each provisioner.

- uap-bastion-provisioner
  - Docker image, running Ansible & CloudFormation to provision and decommission bastion/jumpbox VM for UAP infrastructure.
  - Terraform modules to provision and decommission bastion/jumpbox VM for UAP infrastructure.

- uap-dynamodb-provisioner
  - Docker image, running Ansible & CloudFormation to provision and decommission AWS DynamoDB table used to store client inventory settings.
  - Terraform modules to provision and decommission AWS DynamoDB table used to store client inventory settings.
  
- uap-rds-provisioner
  - Docker image, running Ansible & CloudFormation to provision and decommission UAP AWS RDS stacks.
  - Terraform modules to provision and decommission UAP AWS RDS stacks.

- uap-matillion-provisioner
  - Docker image, running Ansible & CloudFormation to provision and decommission Matillion ETL VM.
  - Terraform modules to provision and decommission Matillion ETL VM.

- uap-kinesis-provisioner
  - Docker image, running Ansible & CloudFormation to provision and decommission Kinesis Firehose.
  - Terraform modules to provision and decommission Kinesis Firehose.

- uap-sns-provisioner
  - Docker image, running Ansible & CloudFormation to spin up an S3 bucket, SNS Topic to be used as part of the event-driven publishing/analytics pipelines.
  - Terraform modules to provision and decommission S3 bucket, SNS Topic.

- uap-sqs-provisioner
  - Docker image, running Ansible & CloudFormation to spin up an S3 bucket, SQS Queues to be used as part of the event-driven publishing/analytics pipelines.
  - Terraform modules to provision and decommission S3 bucket, SQS Queues.

- uap-emr-provisioner
  - Docker image, running Ansible & CloudFormation to provision and decommission AWS EMR cluster.
  - Terraform modules to provision and decommission AWS EMR cluster.

- uap-snowflake-provisioner
  - Docker image, running Ansible & CloudFormation (or Terraform) to provision and decommission AWS EMR cluster.
  - Terraform modules to provision and decommission AWS EMR cluster.

- uap-sagemaker-provisioner
  - Docker image, running Ansible & CloudFormation to provision and decommission AWS SageMaker.
  - Terraform modules to provision and decommission AWS SageMaker.

- uap-tableau-provisioner
  - Docker image, running Ansible & CloudFormation to provision and decommission Tableau Server VM.
  - Terraform modules to provision and decommission Tableau Server VM.

- uap-jenkins-provisioner
  - Docker image, running Ansible & CloudFormation to provision and decommission Jenkins CI/CD for UAP infrastructure.
  - Terraform modules to provision and decommission Jenkins CI/CD for UAP infrastructure.

- uap-elasticsearch-provisioner
  - Docker image, running Ansible & CloudFormation to provision and decommission UAP AWS Managed ElasticSearch clusters.
  - Terraform modules to provision and decommission AWS Managed ElasticSearch clusters.

- uap-msk-provisioner
  - Docker image, running Ansible & CloudFormation to provision and decommission AWS Managed Kafka cluster (MSK).
  - Terraform modules to provision and decommission AWS Managed Kafka cluster (MSK).





