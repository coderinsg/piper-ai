# Introduction
The purpose of lab 1 & 2 is to familiarize participants with basic functionality of Rafay console. This exercise ties together multiple concepts within Rafay to create a useable and tangible outcome. The new understanding aims to encourage and trigger imagination of partipants to extend it with other serviecs.

# Lab objectives
In this exercise, 
1. Participant will play the role of an end-user that request for Kubernetes cluster.
2. Participant will also understand as an Infra admin how components are stitched together to make up an offerings.

# Sections
1. Provision a virtual kubernetes cluster through Rafay Self-Service Console under `Developer Hub`.
2. Run a workload on the newly provisioned virtual kubernetes cluster.

# Practice
## Section 1 - Provision a virtual kubernetes cluster (vCluster)
1. Log in to Dell's console at [https://dell.rafay.dev](https://dell.rafay.dev) <br><br>
2. Click on the nine dots button on the top left. <br>
   Navigate to `Developer Hub`. <br><br>
3. You need create a new workspace, so your new vCluster can be deployed on this workspace. <br>
   Click on the `Workspace` from the menu on the left. <br>
   Then click the `New Workspace` button on the right top of the panel. <br><br>
   ![Create New Workspace](./assets/L1-Workspace.png "Create New Workspace") <br><br>
4. Please consider to provide a unique name for your own workspace. <br>
   You may leave `Display Name` and `Description` empty. <br> 
   Click on the `Save` button. <br>
   ![Create New Workspace](./assets/L1-New-Workspace.png "Create New Workspace") <br><br>
5. Click the `Home` menu from the left panel. <br>
   On the right panel, there are multiple type of services which you can deploy in self-service manner. <br>
   (`Compute`, `Notebooks`, `Inference Endpoints`, `AI/ML Jobs`, `Custom Services`) <br><br>
6. Click the `New Compute Instance` button under the `Compute` Profiles.
   ![Select Compute Instance](./assets/L1-Select-Compute-Instance.png "Select Compute Instance") <br><br>
7. `Lab 1 - vCluster` service template was created by infra administrator. <br>
   Let's create a new compute instance by clicking on `Select` button.
   ![Click Select button](./assets/L1-Select-Compute-Profile.png "Click Select Button") <br><br>
8. Give your new vCluster instance a unique name. <br>
   Select your own created `Workspace`. <br>
   Click `Deploy` button. <br>
   ![A unique name for your vCluster](./assets/L1-vCluster-Name.png) <br><br>
9. The vCluster will start to be provisioned. It's progress can be monitored in `Status Tracker`.
   ![Status panel](./assets/L1-Deploy-In-Progress.png "Deployment in progress ... till Success!") <br><br>
10. Wait till the status turns to `Success` under the `Overview`. <br>
   You shall see the `vCluster` shown under the `Output`. <br>
   Try to note down value of the `vCluster` for the next steps.
   ![Success Deployment](./assets/L1-vCluster-Deployed.png "Success Deployment") <br><br>
11. Click on the nine dots button on the top left. <br>
   Navigate to `Infrastructure`. <br>
   Under  `engcheng-testing ` project on the right, click on `Go to Project` button.
   ![Go To Project](./assets/L1-Go-To-Project.png) <br><br>
12. Click on `My Clusters` menu option on the left. <br>
   Check the running status of the vcluster which you noted down in the previous step, wait until the `Status` shows `HEALTHY`. <br>
   ![Check vCluster Status](./assets/L1-Check-vCluster-Status.png) <br><br>
13. Congratulatons! You have your own virtual kubernetes cluster deployed successfully! <br><br>

## Section 2 - Run a workload on the newly provisioned virtual kubernetes cluster
1. Back to your vCluster under the `My Clusters`, you will see 4 quick access buttons:
![4 quick buttons](./assets/L1-4-Quick-Access-Buttons.png "Quick access buttons")
  - `KUBECTL` - for administrators to interact with the cluster through `kubectl` command
  - `RESOURCES` - to get a quick overview of the resources consumed by the cluster
  - `DASHBOARD` - multiple views of the cluster including general stats and cost related information.
  - `UTILIZATION` - a list of resources types, resource quotas (project and namespace limit) and the limit utilized by each resource operational on a given Kubernetes cluster. <br><br>
2. Click "KUBECTL" button in the same row of your vCluster where a console will be shown below. <br>
   ![Kubectl Console](./assets/L1-Kubectl-Console.png "Kubectl Console")
   The console provides a secure way to interact and issue commands to the cluster with `kubectl` as a prefix, barring other commands. <br><br>
3. Run the command: `kubectl run nginx --image=nginx`. <br>
   The return result `pod/nginx created` shows that pod was created. <br><br>
4. Run the command: `kubectl get pods`. <br>
   Make sure nginx pod is in `running` status. <br><br>
5. The pod is available only internally. Let's make it externally reachable through the command: <br>
   `kubectl expose pod/nginx --port=80 --name nginx --type=LoadBalancer` <br><br>
6. After a brief moment, we can check the result of exposing the service. <br>
   Enter the command: `kubectl get svc nginx`.
   ![Expose nginx](./assets/S3_6.png "Exposing nginx service") <br><br>
7. The successful deployment will see under EXTERNAL-IP having value similar to: <br>
   `a43c1adabd2ce48d1b1b0da378b761bb-2136871209.ap-northeast-1.elb.amazonaws.com` <br><br>
8. Open a browser with the URL indicated. You will see `Welcome to nginx!` <br>
   (`Note`: The classic load balancer from AWS might take 15-20 seconds to be ready, if the first loading is not successful, please wait a while and try again) <br>
   ![Checking nginx](./assets/S3_8.png "Verifying our setup.") <br><br>
9. Congratulation! You've completed deploying a workload on your newly deployed vcluster!
