# Introduction
The purpose of lab 1 & 2 is to familiarize participants with basic functionality of Rafay console. 
This exercise ties together multiple concepts within Rafay to create a useable and tangible outcome.
The new understanding aims to encourage and trigger imagination of partipants to extend it with other serviecs.

# Lab 2 objectives
In this exercise, 
1. Participant will play the role of a Data Scientist / AI Developer.
2. Participant to use `Developer Hub` as the Rafay Self-Service Console to launch a new instance of Jupyterhub. 

# Sections
1. Create a new Jupyterhub instance through `Developer Hub` as the Rafay Self-Service Console.
2. Login to the newly provisioned Jupyerhub instance.

# Practice
## Create a new Jupyterhub instance
1. Log in to Dell's console at [https://dell.rafay.dev](https://dell.rafay.dev)
2. Click on the nine dots button on the top left <br>
   Navigate to `Developer Hub`
3. Over here, click the `New Notebook` button under the `Notebooks` Profiles
![Select Notebook](./assets/L2-Select-Notebook.png "Select Notebook")
4. `Lab 2 - Jupyterhub` service template was created by infra administrator. <br>
   Let's create a new service instance by clicking on `Select` button
![Click Select button](./assets/L2-Select-Notebook-Profiles.png "Click Select Button")
6. Give your new Jupyterhub instance a unique name and click `Deploy` button <br>
   (`Note`: Keep your workspace the same as in Lab 1)
![A unique name for your Jupyterhub](./assets/L2-App-Name.png)
7. The Jupyterhub will start to be provisioned. It's progress can be monitored in `Status Tracker`
![Status panel](./assets/L2-Deploy-In-Progress.png "Deployment in progress ... till Success!")
8. Wait till the status turns to `Success` under the `Overview`. <br>
   You shall see the `URL` and `vCluster` shown under the `Output`. <br>
   Try to note down both the values for the next steps.
![Success Deployment](./assets/L2-JupyterHub-Deployed.png "Success Deployment")
9. Click on the nine dots button on the top left <br>
   Navigate to `Infrastructure`
   Under  `engcheng-testing ` project on the right, click on `Go to Project` button
![Go To Project](./assets/L2-Go-To-Project.png)
10. Click on `My Clusters` menu option on the left <br>
   Check the running status of the vcluster which you noted down in the previous step, wait until the `Status` shows `HEALTHY` <br>
   (`Note:` Your newly deployed JupyterHub is actually runing on a vCluster for security with isolation purpose.)
![Check vCluster Status](./assets/L2-Check-vCluster-Status.png)
11. Congratulatons! You have your own Jupyterhub deployed successfully!

## Login to the newly provisioned JupyerHub instance
1. Open a new browser tab, paste the URL of the JupyterHub on the browser's address bar <br>
   You may key in any `Username` with EMPTY `Password`  <br>
![Jupyterhub login page](./assets/L2-JupyterHub-Landing-Page.png "Jupyterhub login page")
2. After login to the Jupyterhub, click the `Start` button to launch the JupyterLab <br>
![Launch JupyterLab](./assets/L2-Launch-Single-User-JupyterHub.png "Launch JupyterLab")
3. Congratulation! You've completed deploying the JupyterLab from Jupyterhub.
![Success Loading](./assets/L2-JupyterLab-Success-Loading.png)
