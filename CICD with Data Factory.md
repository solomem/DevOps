
# Azure DevOps CI/CD with Data Factory
## Create a Data Factory pipeline in our Azure Portal 
 In this example, we have one simple copy activity. 
* Please note on the upper left hand corner, github is already set as the default repository
* Currently, the branch is pointing at Master
* Click the drop down on the New Branch or [Alt-N]
* Enter a new feature Branch
* Example "Thirdcopybranch Branch"

![pic1](https://user-images.githubusercontent.com/35809983/62907712-18163a80-bd64-11e9-8d99-0fb349925cfe.png)
<br/>
## Make changes to the label of the Copy Activity
* Call the "Copy Data Second Change"
* Click the Publish button

## Interacting with Git
* A message will prompt you to Merge the changes to 'master' first
* This will prompt you to initiate a 'pull request'
* Go to github
* Once the pull request has been initiated, confirm all the merge changes
* Go back to portal Data Factory and switch the branch to 'master'
* Click the Publish button
* This publish will execute the ARM templates to the adf_publish branch

## Go to DevOps
* Connect DevOps to Github
* Go to Project Settings
* Go to Pipelines -> Service connections
* Enter the Personal Access Token 
![image](https://user-images.githubusercontent.com/35809983/62935744-715b8980-bdb7-11e9-829d-0e49c486d43f.png)
<br/>

## Go to Pipelines -> Releases
### Set up Artifacts
* Select GitHub as the Artifacts
* Select default branch as adf_publish
* Default version -> Lastest from the default branch
* On the upper right hand corner of the Artifacts, click the lightning bolt - Continuous integration
### Set up Stages
* Create a job and task
* When creating a job, select an empty job
* This will create an agent job for your pipeline
* Create a Task
* For Data Factory job, choose Azure Resource Group Deployment
* Enter template information
* Update the parameter files based on environmental values
