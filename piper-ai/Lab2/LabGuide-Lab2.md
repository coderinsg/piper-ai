# Introduction
The purpose of lab 1 and lab 2 is to familarize participants with basic functionality of Rafay console. 
This exercise ties together multiple concepts within Rafay to create a useable and tangible outcome.
The new understanding aims to encourage and trigger imagination of partipants to extend it with other serviecs.

# Lab 2 objectives
In this exercise, 
1. Participant will play the role of a Data Scientist / AI Developer.
2. Participant to use Developer Hub as the Rafay Self-Service Console to launch a new instance of JupyterHub. 

# Sections
1. Create a new JupyterHub instance through Developer Hub as the Rafay Self-Service Console.
2. Login to the newly provisioned JupyerHub instance.

# Practice
## Create a new Jupyterhub instance
1. Log in to Dell's console at [https://dell.rafay.dev](https://dell.rafay.dev)
2. Click on the nine dots button on the top left <br>
   Navigate to `Developer Hub`
3. Over here, click the `New Notebook` button under the `Notebooks` Profiles
![Select Notebook](./assets/L2-Select-Notebook.png "Select Notebook")
4. `Lab 2 - Jupyterhub` service was provisioned by administrator to us as a template. Let's create a new service instance by clicking on `Select` button
![Select Notebook Profiles](./assets/L2-Select-Notebook-Profiles.png "Select Notebook Profiles")
5. Give your new Jupyterhub instance a name and click `Deploy` button <br>
   (`Note`: Keep your workspace the same as in Lab 1)
![A unique name for your Jupyterhub](./assets/L2-App-Name.png "Enter Unique App's Name")
6. The Jupyterhub will start to be provisioned. It's progress can be monitored in `Status Tracker`
![Status panel](./assets/L2-Deploy-In-Progress.png "Deployment in progress ... till Success!")
7. Wait till the status turns to `Success` under the `Overview`. <br>
   You shall see the `URL` and `vCluster` shown under the `Output`. <br>
   Try to note down both the values for the next steps.
![Status panel](./assets/L2-JupyterHub-Deployed.png "Updating progress ... till Success!")
8. Click on the nine dots button on the top left <br>
   Navigate to `Infrastructure`
   Under  `engcheng-testing ` project on the right, click on `Go to Project` button
![Go To Project](./assets/L2-Go-To-Project.png)
9. Click on `My Clusters` menu option on the left <br>
   Check the running status of the vcluster which you noted down in the previous step, wait until the `Status` shows `HEALTHY` <br>
   (`Note:` Your newly deployed JupyterHub is runing on a vCluster for security with isolation purpose.
![Check vCluster Status](./assets/L2-Check-vCluster-Status.png)

## Login to the newly provisioned JupyerHub instance
1. Click on the nine dots button and select "Infrastructure"
2. Since the newly created cluster is hosted in "engcheng-testing" project, we will select "Go to project".
![Go to Project](./assets/S2_2.png "Selecting the right project")
3. In the console shows "Infrastructure" -> "Clusters" and the newly created cluster is shown as well. 
![Checking our project](./assets/S2_3png "Our newly created cluster is here!")
4. On the top row, 3 quick access buttons available are:
![3 quick buttons](./assets/S2_4.png "Quick access buttons")
  - "KUBECTL" - for administrators to interact with the cluster through `kubectl` command
  - "RESOURCES" - to get a quick overview of the resources consumed by the cluster
  - "DASHBOARD" - multiple views of the cluster including general stats and cost related information.

## Running workload on the cluster
1. Select "KUBECTL" where a console will be shown below.
2. The console provides a secure way to interact and issue commands to the cluster with "kubectl" as a prefix, barring other commands.
3. Run the command `kubectl run nginx --image=nginx`. The return result `pod/nginx created` shows that pod was created.
4. Using `kubectl get pods`, make sure nginx pod is in `running` status.
5. The pod is available only internally. Let's make it externally reachable through the command:
   `kubectl expose pod/nginx --port=80 --name nginx --type=LoadBalancer`
6. After a brief moment, we can check the result of exposing the service. Enter the command: `kubectl get svc nginx`.
![Expose nginx](./assets/S3_6.png "Exposing nginx service")
7. The successful deployment will see under EXTERNAL-IP having value similar to `a43c1adabd2ce48d1b1b0da378b761bb-2136871209.ap-northeast-1.elb.amazonaws.com`
8. Open a browser with the URL indicated. You will see "Welcome to nginx!".
![Checking nginx](./assets/S3_8.png "Verifying our setup.")
9. Congragulation! You've completed deploying a workload.
