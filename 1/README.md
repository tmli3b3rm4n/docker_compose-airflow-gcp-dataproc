This is intended to be a quickstart for local develompment to tests dags before pushing to production.  It uses docker-compose as an orchastrator and apache airflow as it's base. if you already have docker.  

## Pre-reqs
--

1. Install Docker Community Edition (CE) on your workstation. Depending on the OS, you may need to configure your Docker instance to use 4.00 GB of memory for all containers to run properly. Please refer to the Resources section if using Docker for Windows or Docker for Mac for more information.

2. Install Docker Compose v1.29.1 and newer on your workstation.

#### Default memory is often not enough
You can also check if you have enough memory by running this command:

``docker run --rm "debian:bullseye-slim" bash -c 'numfmt --to iec $(echo $(($(getconf _PHYS_PAGES) * $(getconf PAGE_SIZE))))'`

Should be atleast 8

~Optionally you can enable flower by adding --profile flower option e.g. docker-compose --profile flower up or by explicitly targeted on the command line e.g. docker-compose up flower.~



