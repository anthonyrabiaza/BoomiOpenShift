# Setup of a Dell Boomi Atom on OpenShift

The deployment of the Atom on OpenShift is using a slightly different version of the Boomi Atom for Docker as OpenShift has it's own constraints (the Pod will be assigned with a user ID, root user cannot be used to run an image...).

I created a custom image to cope with the different constraints and allow the deployment of an Atom in OpenShift:  https://cloud.docker.com/repository/docker/anthonyrabiaza/openshift-boomi-atom/general

# Deployment of the Service

Connect to OpenShift Console and select Networking>Services

![](resources/services.png)

Click on "Create Service " and copy-paste the content of [service](atom/boomi-atom-service.yaml?raw=true)

![](resources/services_done.png)

Click on "Create"

![](resources/services_view.png)



# Deployment of Boomi Atom on OpenShift

Click on Workloads>Deployments

Click on “Create Deployment”

![](resources/deployments.png)

Click on "Create Deployment " and copy-paste the content of [deployment](boomi-atom-deployment.yaml?raw=true). Then replace the values wrapped in @@REPLACEME@@

![](resources/deployments_done.png)

You will see the new deployment with 1 Pod requested:

![](resources/deployments_view.png)

Click on "Pods"

[](resources/deployments_view_pods.png)

