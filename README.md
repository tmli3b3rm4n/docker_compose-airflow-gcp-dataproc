This is intended to be a quickstart for local develompment to tests dags before pusing to production.  This is not intended to be used as a production solution.  This will set up a local Apache Airflow using docker-compose.  

## Pre-reqs
--

1. Install Docker Community Edition (CE) on your workstation. Depending on the OS, you may need to configure your Docker instance to use 4.00 GB of memory for all containers to run properly. Please refer to the Resources section if using Docker for Windows or Docker for Mac for more information.

2. Install Docker Compose v1.29.1 and newer on your workstation.

#### Default memory is often not enough
You can also check if you have enough memory by running this command:

## Quick Start
Initialize the database
`docker-compose up airflow-init`

After initialization is complete, you should see a message like below.

```
airflow-init_1       | Upgrades done
airflow-init_1       | Admin user airflow created
airflow-init_1       | 2.3.2
start_airflow-init_1 exited with code 0
```
Now you can start all services.
`docker-compose up` or optionally `docker-compose --profile flower up`


## Running 
``docker run --rm "debian:bullseye-slim" bash -c 'numfmt --to iec $(echo $(($(getconf _PHYS_PAGES) * $(getconf PAGE_SIZE))))'`

Should be atleast 8g


Optionally you can enable flower by adding --profile flower option e.g. docker-compose --profile flower up or by explicitly targeted on the command line e.g. docker-compose up flower.


## Notes:
Some directories in the container are mounted, which means that their contents are synchronized between your computer and the container.

./dags - you can put your DAG files here.

./logs - contains logs from task execution and scheduler.

./plugins - you can put your custom plugins here.

## Loggin in
The account created has the login airflow and the password airflow.



