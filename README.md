# Technical Session
----------

## Preparing for the workshop
### Instructor requirements:
- Being very comfortable with 3scale both in terms of configuration and of operations. Knowing the basics of the Developer Portal
- Being comfortable with RH SSO and especially around OpenID Connect protocol
- Being able to use Postman (or similar REST client) to build REST request and REST authentication
- Having a basic knowledge of OpenShift
- For the Fuse Online section, two options are available:
  - A Fuse Online account, sign up [here](https://www.openshift.com/products/fuse) using your Employee sub
  - Using the local [installation](https://github.com/syndesisio/syndesis/tree/master/install) with minishift following these instructions
  Once you have minishift running use this commands to create the syndesis app:
    
    `oc new-project syndesis`

    `oc create -f support/serviceaccount-as-oauthclient-restricted.yml`

    `oc create -f syndesis.yml`

    `oc new-app --template=syndesis  -p ROUTE_HOSTNAME=syndesis.<local_minishift_cluster_address>.nip.io  -p OPENSHIFT_MASTER=$(oc whoami --show-server)  -p OPENSHIFT_PROJECT=$(oc project -q)  -p OPENSHIFT_OAUTH_CLIENT_SECRET=$(oc sa get-token syndesis-oauth-client) -p DEMO_DATA_ENABLED=true -p CONTROLLERS_EXPOSE_VIA3SCALE=true -p SAR_PROJECT=$(oc project -q)`

    Once syndesis is running locally you can use ngrok (https://ngrok.com/) to expose the integration externally



### Attendees requirements:
Everybody needs:
- a [supported](https://docs.openshift.com/container-platform/3.11/architecture/infrastructure_components/web_console.html#browser-requirements) browser 
- basic knowledge of REST protocol
- basic knowledge of containers
- basic understanding of OAuth social applications

----------

### Environment:
#### TODO
----------

### Duration & format
This is a workshop designed for approximately 2 hours delivery. The focus is on the adoption of the products in the financial industry. This is not an introduction to the different products used in the environment, but it is focused on the modules and functionalities relevant for the FSI case. Typically, instructors would talk through the introduction slides, and then for each hands-on lab, perform the steps needed to achieve the objective of the lab with reference to content in the slides or here. At the end of each activity there will be a checkpoint.

### Timeline
| Duration        | Content           | Link  |
| ------------- |:-------------:| -----:|
| col 3 is      | right-aligned | $1600 |
| col 2 is      | centered      |   $12 |
| zebra stripes | are neat      |    $1 |


-------------
## Lab instructions
### Practical Part 1
#### Integr8ly
#### Fuse Online
#### 3scale
### Checkpoint
#### RH SSO & 3scale
### Checkpoint
### Break
### Practical Part 2
#### OpenShift
### Q&A
---------------
### Common issues
