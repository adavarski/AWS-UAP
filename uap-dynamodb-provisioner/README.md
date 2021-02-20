### DynamoDB Provisioner

Provisions DynamoDB table that will be used to store UAP client settings.

#### Provisioning a new UAP DynamoDB table

```sh
cd dynamodb

make build-provisioner

# Fill in the AWS credentials and region e.g. us-east-2
# The credentials should be for the IAM provisioner user (uap-provisioner)
export AWS_ACCESS_KEY_ID="xxx"
export AWS_SECRET_ACCESS_KEY="xxx"
export AWS_REGION="us-east-2"

# Fill in the required details e.g. for staging environment
export ENVIRONMENT_NAME="staging"
export ENVIRONMENT_TYPE="d"

make provision-dynamodb
```
Example Output:
```
$ make provision-dynamodb
[WARNING]: No inventory was parsed, only implicit localhost is available
[WARNING]: provided hosts list is empty, only localhost is available. Note that the implicit localhost does not match 'all'

PLAY [Provision UAP DynamoDB] ********************************************************************************************************************************************************************

TASK [Gathering Facts] ***************************************************************************************************************************************************************************
ok: [localhost]

TASK [Apply CloudFormation stack] ****************************************************************************************************************************************************************
changed: [localhost]

PLAY RECAP ***************************************************************************************************************************************************************************************
localhost                  : ok=2    changed=1    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0   
```

#### Decommissioning UAP DynamoDB table

```sh
cd dynamodb

make build-provisioner

# Fill in the AWS credentials and region e.g. us-east2-
# The credentials should be for the IAM provisioner user (uap-provisioner)
export AWS_ACCESS_KEY_ID="xxx"
export AWS_SECRET_ACCESS_KEY="xxx"
export AWS_REGION="us-east-2"

# Fill in the required details e.g. for staging environment
export ENVIRONMENT_NAME="staging"

make decommission-dynamodb
```
Example Output:
```
$ make decommission-dynamodb
[WARNING]: No inventory was parsed, only implicit localhost is available
[WARNING]: provided hosts list is empty, only localhost is available. Note that the implicit localhost does not match 'all'

PLAY [Decommission UAP DynamoDB] *****************************************************************************************************************************************************************

TASK [Gathering Facts] ***************************************************************************************************************************************************************************
ok: [localhost]

TASK [Delete CloudFormation stack] ***************************************************************************************************************************************************************
changed: [localhost]

PLAY RECAP ***************************************************************************************************************************************************************************************
localhost                  : ok=2    changed=1    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0   
```

Check:
```
$ aws dynamodb list-tables
```
