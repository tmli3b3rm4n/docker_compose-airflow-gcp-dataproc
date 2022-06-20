This is intended to be a quickstart for local develompment to tests dags using dataproc before pusing to production. This is a focused cliff note of using dataproc with airflow.  Everything contained is taken from apache docs. This is not intended to be used as a production solution.  This will set up a local Apache Airflow using docker-compose and load in any dags located in the DAG directory.  "./dags".  To run follow instructions exactly.  If you mess up installation run 
`$ docker-compose down --volumes --remove-orphans`.

## Prerequisites

1. Install Docker Community Edition (CE) on your workstation. Depending on the OS, you may need to configure your Docker instance to use 4.00 GB of memory for all containers to run properly. Please refer to the Resources section if using Docker for Windows or Docker for Mac for more information.

2. Install Docker Compose v1.29.1 and newer on your workstation.

**Default memory is often not enough.  You want atleast 8gb.** 
You can also check to see if you have enough memory by running this command:
```
docker run --rm "debian:bullseye-slim" bash -c 'numfmt --to iec $(echo $(($(getconf _PHYS_PAGES) * $(getconf PAGE_SIZE))))'
```
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

## Login

<a href="http://localhost:8080/home">localhost:8080/home</a>

The account created has the folowing login. Username **`airflow`** and the password **`airflow`**.

## Connecting Service Account
1. Open your browser and navigate to the <a href="http://localhost:8080/home">Airflow</a> page.
2. Using the main navigation drop down the admin menu and select `connections`
   * `navigation -> admin -> connection`
3. Hit the `+` button followed by filling in the form.
4. Test connection and submit. 

## Testing your DAG
From the home page you should see your dag.  You can use options menu from row to trigger DAG.  

Anything deeper then this you can refer to airflow documentation.  Again this is only for local testing.

## Notes:
--
Some directories in the container are mounted, which means that their contents are synchronized between your computer and the container.

./dags - you can put your DAG files here.

./logs - contains logs from task execution and scheduler.

./plugins - you can put your custom plugins here.






