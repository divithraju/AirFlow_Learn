# Airflow Installation Steps for Linux

Step 1: Update Your System

sudo apt update

## Step 2: Install Python and Virtual Environment

sudo apt install python3 python3-pip

Install virtualenv:

sudo pip3 install virtualenv

## Step 3: Create and Activate a Virtual Environment

mkdir airflow_project

cd airflow_project

Create a virtual environment:

virtualenv airflow_venv 

source airflow_venv/bin/activate

## Step 4: Install Apache Airflow with Constraints Set Airflow constraints:

AIRFLOW_VERSION=2.6.2 PYTHON_VERSION="$(python --version | cut -d " " -f 2 | cut -d "." -f 1-2)" CONSTRAINT_URL="https://raw.githubusercontent.com/apache/airflow/constraints-${AIRFLOW_VERSION}/constraints-${PYTHON_VERSION}.txt"

Install Apache Airflow using constraints:

pip install "apache-airflow==${AIRFLOW_VERSION}" --constraint "${CONSTRAINT_URL}"


## Step 5: Initialize the Database

Set the Airflow home directory:

export AIRFLOW_HOME=~/airflow

Initialize the database:

airflow db init


## Step 6: Start Airflow

Start the web server:

airflow webserver --port 8082

source ~/airflow_project/airflow_venv/bin/activate airflow scheduler

Accessing Airflow http://localhost:8082



## Additional Steps Set up the Airflow user (Optional):

airflow users create
--username admin

--firstname divith

--lastname raju

--role Admin

--email demo@admin.com


