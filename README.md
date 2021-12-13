# Implementation Diagram
![diagram](https://raw.githubusercontent.com/GNUKalashnikov/jenkins/main/images/jenkins.svg)
---
![initial implementation](https://raw.githubusercontent.com/GNUKalashnikov/jenkins/8937b4bceec4a15c6e8b5abd5fceb950017c0c79/jenkins.svg)
# CI/CD

CI/CD is a method to frequently deliver apps to customers by introducing automation into the stages of app development. The main concepts attributed to CI/CD are continuous integration, continuous delivery, and continuous deployment. CI/CD is a solution to the problems integrating new code can cause for development and operations teams

# Jenkins

The automation engine within CI/CD, the ability to generate jobs, tasks or linux commands progressivly is the key aspect to jenkins.
the software development pipeline such as building, testing, and deployment, helps in implementing the processes of Continuous Integration and Continuous Deployment/Continuous Delivery of projects

# Instructions

## SSH

```shell
$ ssh-keygen -t ed25519 -C "your_email@example.com"
```

A *Linux* way to create a SSH key.

1. Go to the related repository
2. Upon the main page click on the settings 
3. Deploy keys
4. ![ssh](https://github.com/GNUKalashnikov/jenkins/blob/main/images/Screenshot_20211210_091951.png?raw=true)

### Webhook

1. Whilst within the settings of the application
2. Find *Webhooks*
3. ![webhook](https://github.com/GNUKalashnikov/jenkins/blob/main/images/webhook.png?raw=true)
4. Make sure to add the *github-webook* suffix
5. update webhook

### Jenkins

**Take note**
Jenkins is an integral part of the CI/CD pipeline
The automation occurs within the jobs we create
1. new item
2. ![jenkins](https://github.com/GNUKalashnikov/jenkins/blob/main/images/jenkinsjob.png?raw=true)
3. free style project

Congratulations, you're on the Jenkins job initialisation.

1. Add a Description
2. Enable Discard old builds and limit the max to 3
3. enable GitHub

The result should be *something like* **this**
![configuration](https://github.com/GNUKalashnikov/jenkins/blob/main/images/jenkins-conf.png?raw=true)
#### Source Code Management

![scm](https://github.com/GNUKalashnikov/jenkins/blob/main/images/source-code.png?raw=true)

This is where you would set up your GitHub information.
Take note of the credentials section, this would be the private version of the same key we used earlier for the creation of the SSH on GitHub.
Indication toward the branches to build section, make sure this is the branch that is in use and is correctly entered.

#### build
Within this section belongs a kind of translator and or provissionor depending on the use case.
From my example will be focused on executing shell commands.
This works as a translator by git cloning the file into a area within Jenkins whereby the command list is applied sequentially.

![build](https://github.com/GNUKalashnikov/jenkins/blob/main/images/build.png)

#### git publisher
insert image
A useful plugins to be able to push, tag, note, and mergers

I have set up in the image a way to merge from my dev branch into the main.

![git](https://github.com/GNUKalashnikov/jenkins/blob/main/images/git%20-jenk.png?raw=true)

#### job screen
![job](https://github.com/GNUKalashnikov/jenkins/blob/main/images/jenkins-job-main.png?raw=true)

This is the main area of operations for any job.
The main parts to cover are:
* Workspace
    * The location of the repo is stored within this directory
* Build Now
    * initiates the parameters of the job resulting in a success (indicated by sun) or a fail indicated by (stormy clouds)
* Configure
    * Takes the user back into the configuration page.
