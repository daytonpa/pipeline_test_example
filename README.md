# pipeline_test_example

## About
A simple repository project for showing the process of a Multibranch Pipeline within Jenkins.  This project assumes you already have an active Jenkins service.  If not, follow [this guide](https://www.digitalocean.com/community/tutorials/how-to-install-jenkins-on-ubuntu-18-04) to get one started.  If Docker is your flavor of jazz, [follow this guide](https://github.com/jenkinsci/docker/blob/master/README.md) instead.

## How-To

1) Install the [Pipeline Multibranch](https://plugins.jenkins.io/workflow-multibranch) on your Jenkins server
  - This can be done by navigating to the **Manage Jenkins** -> **Manage Plugins** page.
    - Search for "Pipeline multibranch", and you should see one with defaults.
    - Install it.
    - Safely restart your Jenkins service
2) Create a new Job by clicking **New Item**, and enter an item name.  Select **Multibranch Pipeline** for the Project type.

3) Next, you'll be sent to the Job's **Configure** Page.  Fill out the following values:
  - **Display Name**
    - A name to be displayed for your Project within the Jenkins Dashboard
  - **Description**
    - A quick blurb about the Project
  - **Branch Source**
    - Everything "source control" that will trigger jobs.
      - Select **Git**
      - Provide your repository's Git address for the **Project Repository**
      - Under **Behaviors**, select **Add**
        - Add *Discover tags*
        - Add *Filter by name (with wildcards)*
        - *Include* branches you wish to watch
        - *Exclude* branches you wish to avoid
        - Branches are separated by spaces
  - **Build Configuration**
    - Default is "Jenkinsfile" under **Script Path**
      - Make sure the desired Jenkinsfile filename matches the one inside your Project's Git repository.
  - Click **Save**

  Your Pipeline Job is ready to start working.
