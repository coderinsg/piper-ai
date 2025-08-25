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
![Select Notebook](./assets/L2-Select-Notebook.png | width=100)
4. `Lab 2 - Jupyterhub` service was provisioned by administrator to us as a template. Let's create a new service instance by clicking on `Select` button
![Select Notebook Profiles](./assets/L2-Select-Notebook-Profiles.png | width=100)
5. Give your new Jupyterhub instance a name and click `Deploy` button <br>
   (`Note`: Keep your workspace the same as in Lab 1)
![A unique name for your Jupyterhub](./assets/L2-App-Name.png | width=100)
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
   (`Note:` Your newly deployed JupyterHub is runing on a vCluster for security with isolation purpose.)
![Check vCluster Status](./assets/L2-Check-vCluster-Status.png)
10. Congratulatons! You have your own JupyterHub deployed successfully!

## Login to the newly provisioned JupyerHub instance
1. Open a new browser tab, paste the URL of the JupyterHub on the browser's address bar <br>
   You may key in any `Username` with EMPTY `Password`  <br>
![JupyterHub login page](./assets/L2-JupyterHub-Landing-Page.png)
2. After login to the JupyterHub, click the `Start` button to launch the JupyterLab <br>
![Launch JupyterLab](./assets/L2-Launch-Single-User-JupyterHub.png)
3. Congragulation! You've completed deploying the JupyterHub with JupyterLab.
![Success Loading](./assets/L2-JupyterLab-Success-Loading.png)
