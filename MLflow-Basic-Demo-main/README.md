# MLflow-Basic-Demo


## For Dagshub:
Remove the signature part and add dagshub URI in the main file. 

Export the command, open mlflow URI, and run example.py

MLFLOW_TRACKING_URI=https://dagshub.com/entbappy/MLflow-Basic-Demo.mlflow \
MLFLOW_TRACKING_USERNAME=entbappy \
MLFLOW_TRACKING_PASSWORD=6824692c47a369aa6f9eac5b10041d5c8edbcef0 \
python script.py



```bash

export MLFLOW_TRACKING_URI=https://dagshub.com/siddharthtyagi/MLflow-Basic-Demo.mlflow

export MLFLOW_TRACKING_USERNAME=siddharthtyagi

export MLFLOW_TRACKING_PASSWORD=6824692c47a369aa6f9eac5b10041d5c8edbcef0


```
After the above step Go to MLFLOW UI

# MLflow on AWS

## MLflow on AWS Setup:

1. log in to the AWS console.
2. Create an IAM user with AdministratorAccess
3. Export the credentials in your AWS CLI by running "aws configure"
4. Create an s3 bucket
5. Create an EC2 machine (Ubuntu) & add Security groups 5000 port

Run the following command on the EC2 machine
```bash
sudo apt update

sudo apt install python3-pip

sudo pip3 install pipenv

sudo pip3 install virtualenv

mkdir mlflow

cd mlflow

pipenv install mlflow

pipenv install awscli

pipenv install boto3

pipenv shell


## Then set AWS credentials
aws configure


#Finally 
mlflow server -h 0.0.0.0 --default-artifact-root s3://mlflow-test-23

#open Public IPv4 DNS to port 5000


#set uri in your local terminal and in your code 
export MLFLOW_TRACKING_URI=http://ec2-54-147-36-34.compute-1.amazonaws.com:5000/

python example.py
```


