# OTA Community Edition In Google Compute Engine

## Build container

~~~
  ./contrib/gcloud/docker-build.sh
~~~

## Initialze gcloud Environment

A few commands need to be run to set up gcloud credentials:
~~~
 EXTRA_ARGS="-it" ./contrib/gcloud/gcloud auth login

 ./contrib/gcloud/gcloud config set project <YOUR PROJECT>
 ./contrib/gcloud/gcloud config set compute/zone us-central1-c
~~~

## Create Cluster

Create the k8s cluster with:
~~~
 ./contrib/gcloud/gcloud container clusters create ota-ce --machine-type n1-standard-2
 ./contrib/gcloud/gcloud container clusters get-credentials ota-ce
~~~

## Cleaning Up
The setup can be completed removed with:
~~~
  # delete the cluster
  ./contrib/gcloud/gcloud container clusters delete ota-ce --quiet
~~~

