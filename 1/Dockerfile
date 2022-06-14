# FROM golang:1.16 as base

# FROM base as dev

# RUN curl -sSfL https://raw.githubusercontent.com/cosmtrek/air/master/install.sh | sh -s -- -b $(go env GOPATH)/bin

# WORKDIR /opt/app/api
# CMD ["air"]

FROM apache/airflow
RUN pip install --user root
ENV AIRFLOW_HOME=/usr/local/airflow

