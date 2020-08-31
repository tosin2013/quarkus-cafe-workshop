Quarkus Cafe Workshop
=====================

Integration  of Quarkus Cafe with a 3rd party delivery service.  Using Quarkus, AMQ Streams (Kafka), and MongoDB. Running in OpenShift (Kubernetes.)

## Prerequisites
* OCP 4 
* Ansible 2.9
* CRW

## Exercises
* Setting up environment 
  * Push from code.quarkus.io to github repo
  * Or git clone code example from ...
  * Setup up code ready workspaces 
* Creating and testing rest endpoints
* Create a Panache Entity
* Marshall from Incoming to Outgoing entity

## OpenShift prerequisites 
* Install CodeReady WorkSpaces  
  * Install CodeReady Workspaces using the Operator

**prerequisites for CRW Ansible role**
* install ansible
* install openshift cli
* install the pip dependancies 
```
pip3 install kubernetes
pip3 install openshift
```

## quarkus-cafe-workshop deployment Instructions
**Clone quarkus-cafe-workshop repo**
```
git clone https://github.com/tosin2013/quarkus-cafe-workshop.git
```

**cd into  quarkus-cafe-workshop folder**
```
cd quarkus-cafe-workshop
```

## Deploy multi-user workshop
**Create project**
```
oc new-project workshop
```

**Create hosted workshop deployment**
```
.workshop/scripts/deploy-spawner.sh --settings=hosted-workshop
```

**Access deployment**
```
oc get route/quarkus-cafe-workshop
```

**Access the workshop**
```
username: openshiftusername
password: openshiftpassword
```

**Destroy hosted workshop deployment**
```
.workshop/scripts/delete-spawner.sh --settings=hosted-workshop
```


## How to test/develop on OpenShift

**Create project**
```
oc new-project workshop
```

**Create personal workshop deployment**
```
.workshop/scripts/deploy-personal.sh --settings=develop
```

**Build workshop deployment**
```
.workshop/scripts/build-workshop.sh
```

**Access deployment**
```
oc get route/quarkus-cafe-workshop
```

**Access the workshop**
```
username: workshop 
password: workshop
```

**Destroy personal workshop deployment**
```
.workshop/scripts/delete-personal.sh --settings=develop
```

## Local deployment and development Steps 
[Local Deployment Steps](.workshop/scripts)