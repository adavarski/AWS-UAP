# DynamoDB Provisioner

Provisions DynamoDB table that will be used to store UAP client settings.

## Provisioning a new UAP DynamoDB table

```sh
cd dynamodb

make build-provisioner

# Fill in the AWS credentials and region e.g. us-east-2
# The credentials should be for the "uap-provisioner" user
export AWS_ACCESS_KEY_ID="xxx"
export AWS_SECRET_ACCESS_KEY="xxx"
export AWS_REGION="us-east-2"

# Fill in the required details e.g. for staging environment
export ENVIRONMENT_NAME="staging"
export ENVIRONMENT_TYPE="d"

make provision-dynamodb
```

## Decommissioning UAP DynamoDB table

```sh
cd dynamodb

make build-provisioner

# Fill in the AWS credentials and region e.g. us-east2-
# The credentials should be for the "uap-provisioner" user
export AWS_ACCESS_KEY_ID="xxx"
export AWS_SECRET_ACCESS_KEY="xxx"
export AWS_REGION="us-east-2"

# Fill in the required details e.g. for staging environment
export ENVIRONMENT_NAME="staging"

make decommission-dynamodb
```
