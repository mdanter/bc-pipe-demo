# Jenkinsfile based OCP Build strategy demo

## Quickstart
### clone this repository

`cd bc-pipe-demo/app1`

### log in to your cluster

`oc login`


### Review and  apply the buildconfig
Take a look at the yaml file. It references a git repository, demonstrates how to map parameters, and how to reference a stand-alone Jenkinsfile.  

`oc apply -f app1/pipe.yaml`

### start Jenkins based builds

`oc start-build bc/bc-pipe-demo`

## How to make changes
The single source of truth becomes the Jenkinsfile referenced by the build config yaml, along with the same. In order to make changes, commit and push your changes, and respctively use `oc apply -f app1/pipe.yaml`  and start a new build with `oc start-build bc/bc-pipe-demo`.
