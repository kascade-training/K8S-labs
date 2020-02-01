Taks for Core Concepts (13%)

* Create a namespace called 'ghazela' and a pod with image nginx called nginx on this namespace.
* Create the pod that was just described using YAML
* Create a busybox pod (using kubectl command) that runs the command "env". Run it and see the output.
* Get the YAML for a new namespace called 'myns' without creating it
* Get the YAML for a new ResourceQuota called 'myrq' with hard limits of 1 CPU, 1G memory and 2 pods without creating it
* Get pods on all namespaces
* Create a pod with image nginx called nginx and allow traffic on port 80
* Change pod's image to nginx:1.7.1. Observe that the pod will be killed and recreated as soon as the image gets pulled
* Get nginx pod's ip created in previous step, use a temp busybox image to wget its '/'. Get pod's YAML.
* Get information about the pod, including details about potential issues (e.g. pod hasn't started)
* Get pod logs
* If pod crashed and restarted, get logs about the previous instance
* Execute a simple shell on the nginx pod
* Create a busybox pod that echoes 'hello world' and then exits
* Do the same, but have the pod deleted automatically when it's completed
* Create an nginx pod and set an env value as 'var1=val1'. Check the env value existence within the pod


* Create a Pod with two containers, both with image busybox and command "echo hello; sleep 3600". Connect to the second container and run 'ls'
* Create 3 pods with names nginx1,nginx2,nginx3. All of them should have the label app=v1
* Show all labels of the pods
* Change the labels of pod 'nginx2' to be app=v2
* Get the label 'app' for the pods
* Get only the 'app=v2' pods
* Remove the 'app' label from the pods we created before
* Create a pod that will be deployed to a Node that has the label 'accelerator=nvidia-tesla-p100'
* Annotate pods nginx1, nginx2, nginx3 with "description='my description'" value
* Check the annotations for pod nginx1
* Remove the annotations for these three pods
* Remove these pods to have a clean state in your cluster
* Create a deployment with image nginx:1.7.8, called nginx, having 2 replicas, defining port 80 as the port that this container exposes (don't create a service for this deployment)
* View the YAML of this deployment
* View the YAML of the replica set that was created by this deployment
* Get the YAML for one of the pods
* Check how the deployment rollout is going
* Update the nginx image to nginx:1.7.9
* Check the rollout history and confirm that the replicas are OK
* Undo the latest rollout and verify that new pods have the old image (nginx:1.7.8)
* Do an on purpose update of the deployment with a wrong image nginx:1.91
* Verify that something's wrong with the rollout
* Return the deployment to the second revision (number 2) and verify the image is nginx:1.7.9
* Check the details of the fourth revision (number 4)
* Scale the deployment to 5 replicas
* Autoscale the deployment, pods between 5 and 10, targetting CPU utilization at 80%
* Pause the rollout of the deployment
* Update the image to nginx:1.9.1 and check that there's nothing going on, since we paused the rollout
* Resume the rollout and check that the nginx:1.9.1 image has been applied
* Delete the deployment and the horizontal pod autoscaler you created

Jobs: 

* Create a job with image perl that runs the command with arguments "perl -Mbignum=bpi -wle 'print bpi(2000)'"
* Wait till it's done, get the output
* Create a job with the image busybox that executes the command 'echo hello;sleep 30;echo world'
* Follow the logs for the pod (you'll wait for 30 seconds)
* See the status of the job, describe it and see the logs
* Delete the job
* Create a job but ensure that it will be automatically terminated by kubernetes if it takes more than 30 seconds to execute
* Create the same job, make it run 5 times, one after the other. Verify its status and delete it
* Create the same job, but make it run 5 parallel times

Cron jobs
* Create a cron job with image busybox that runs on a schedule of "*/1 * * * *" and writes 'date; echo Hello from the Kubernetes cluster' to standard output
* See its logs and delete it

ConfigMaps:

* Create a configmap named config with values foo=lala,foo2=lolo
* Display its values
* Create and display a configmap from a file
* Create and display a configmap from a .env file
* Create and display a configmap from a file, giving the key 'special'
* Create a configMap called 'options' with the value var5=val5. Create a new nginx pod that loads the value from variable 'var5' in an env variable called 'option'
* Create a configMap 'anotherone' with values 'var6=val6', 'var7=val7'. Load this configMap as env variables into a new nginx pod
* Create a configMap 'anotherone' with values 'var6=val6', 'var7=val7'. Load this configMap as env variables into a new nginx pod

Requests and limits:
* Create an nginx pod with requests cpu=100m,memory=256Mi and limits cpu=200m,memory=512Mi

Secrets:
* Create a secret called mysecret with the values password=mypass
* Create a secret called mysecret2 that gets key/value from a file
* Get the value of mysecret2
* Create an nginx pod that mounts the secret mysecret2 in a volume on path /etc/foo
* Delete the pod you just created and mount the variable 'username' from secret mysecret2 onto a new nginx pod in env variable called 'USERNAME'



ServiceAccounts:
* See all the service accounts of the cluster in all namespaces
* Create a new serviceaccount called 'myuser'
* Create an nginx pod that uses 'myuser' as a service account



Misc:
* Backup the etcd database at /opt/baks/
