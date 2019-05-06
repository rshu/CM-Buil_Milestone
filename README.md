# CM-Build_Milestone
First  milestone of group project for CSC - 519

Team member
* Nawshin Tabassum - ntabass
* Joymallya Chakraborty - jchakra
* Rui Shu - rshu
* Pingping Chen - pchen23
 

In this milestone, the following tasks are completed:

1. *Provisioning* and *configuring* an jenkins server (on a remote VM), automatically using ansible.
2. Using a combination of (jenkins-job-builder or Jenkinsfile) and ansible, automatically setup build jobs for two applications:
  * A nodejs web application [checkbox.io](https://github.com/chrisparnin/checkbox.io).
  * An "enterprise" Java system [iTrust](https://github.ncsu.edu/engr-csc326-staff/iTrust2-v4)
3. Using a combination of mocha/pm2, create a test script that will start and stop the checkbox.io service on the server. A starting place might be [the App](https://github.com/CSC-DevOps/App/blob/master/test/simple.js) we used in the Pipelines workshop.
4. Create a simple git hook or GitHub webhook to trigger a build when a push is made to the repo.   _You may use a forked/cloned version of the two systems._ Demonstrate a passing build for each job after a commit.
  
### Environment Required
Ubuntu Server 16.04 LTS


###Instructions to run the project
Before you start:
`git clone https://github.ncsu.edu/jchakra/CM-Build_Milestone.git `
`cd CM-Build_Milestone `



#### Provisioning and configuring an jenkins server 
We ran all the steps automatically through ansible scripts. 
Our filesystem is structured in roles. 
We have a [playbook.yml](https://github.ncsu.edu/jchakra/CM-Build_Milestone/blob/master/servers/ansible-srv/playbook.yml) file that runs all the roles sequentially.
roles
- jenkins
- install
- jobs


The [jenkins](https://github.ncsu.edu/jchakra/CM-Build_Milestone/blob/master/servers/ansible-srv/roles/jenkins/tasks/main.yml) role is used to install and setup the jenkins server. 

The [install](https://github.ncsu.edu/jchakra/CM-Build_Milestone/blob/master/servers/ansible-srv/roles/install/tasks/main.yml) role is used to install every dependencies needed to run the apps. 

The [jobs](https://github.ncsu.edu/jchakra/CM-Build_Milestone/blob/master/servers/ansible-srv/roles/jobs/tasks/main.yml) role is used to update the all the jenkins job which is controlled by git hook.

#### Set Up iTrust with details

[iTrust](https://github.com/rshu/iTrust) We have translate all the steps into ansible scripts.

#### Set Up Checkbox.io with details

[checkbox.io](https://github.com/rshu/checkbox.io) We have translate all the steps into ansible scripts.

#### Jenkins job building

![image](https://github.ncsu.edu/jchakra/CM-Build_Milestone/blob/master/iTrust.png)

![image](https://github.ncsu.edu/jchakra/CM-Build_Milestone/blob/master/checkbox.png)


#### Git hook
The git hook code is provided in this [file](https://github.ncsu.edu/jchakra/CM-Build_Milestone/blob/master/servers/ansible-srv/post-receive)

For the demo, please visit 

[Google Drive Links](https://drive.google.com/file/d/1LtUyfm7oyUOZzF-A2yhz8NBYzcSHLwQM/view?usp=sharing)

