# aws-ansible-provisioning


---
This script initially questions the user for their AWS credentials and records the values in the aws access key and aws secret key variables. It then prompts the user for the type of AWS infrastructure they wish to build and keeps the response in the infrastructure variable. Finally, it runs multiple tasks dependent on the value of the infrastructure variable, using the aws access key and aws secret key variables to authenticate the AWS modules.


---
This Ansible playbook accomplishes the following:

Prompts the user for their AWS access key and secret key. These credentials are needed to authenticate with the AWS API and perform operations on their behalf.

Prompts the user for the sort of AWS infrastructure they want to build. The alternatives are 'ec2', 'rds', or 's3'.

Based on the user's selection, it builds the specified AWS infrastructure.

1. If the user selects 'ec2', it creates an EC2 instance using the 'ec2' module.
2. If the user selects 'rds', it creates an RDS instance using the 'rds' module.
3. If the user selects 's3', it creates an S3 bucket using the 's3' module.
4. The playbook uses variables to store the user's input and pass it to the relevant tasks. The 'when' condition is used to specify that a task should only be run if the specified condition is true. In this case, the tasks are only run if the value of the 'infrastructure' variable matches the value specified in the 'when' condition.
