# Assignment 2 - DynamoDB CRUD Application

## Architecture
User → EC2 → DynamoDB

## EC2 Setup
1. Used existing Ubuntu EC2 instance (same as Lab 5)
2. Connected via SSH
3. Installed Python and pip:
   
   sudo apt update
    
   sudo apt install python3 python3-pip -y
   
5. Created virtual environment:
   
   python3 -m venv myenv
   
   source myenv/bin/activate
7. Installed boto3:
   
   pip install boto3

---

## DynamoDB Setup
1. Created DynamoDB table:
   - Table Name: students
   - Partition Key: id (String)
2. Capacity Mode: On-demand (default)
3. Table status: Active

---

## IAM Setup
1. Created IAM role: dynamodb-ec2-role
2. Attached policy:
   - AmazonDynamoDBFullAccess
3. Attached role to EC2 instance

---

## Connecting EC2 to DynamoDB
Python code used:

import boto3 

dynamodb = boto3.resource('dynamodb', region_name='eu-north-1') 

table = dynamodb.Table('students')

---

## CRUD Operations

- Create:
  Inserted item using put_item()

- Read:
  Retrieved item using get_item()

- Update:
  Modified item using update_item()

- Delete:
  Removed item using delete_item()

All operations performed successfully on DynamoDB.

---

## Data Types Used
- String → id, name
- Number → age
- Boolean → active
- List → subjects
- Map → address

---

## Security
- Used IAM role for EC2 → DynamoDB access
- No AWS access keys used in code
- Secure communication via AWS IAM

---

## Result
Successfully implemented a DynamoDB-based application on EC2 with full CRUD functionality and secure IAM-based access.
