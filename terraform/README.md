IaC - Terraform 

What is IaC?
Tool to manage infrasturuture in a conisistent way through code 
Provisioning infrasturucture through software to achieve consisten and predictable envirnoments 
Code deploys infa consistently so the environment created is predictable 


Core Concepts 
- Defined in code (JSON, YAML, Terraform)
- Defined in Source Control 
- Declarative or Imperative 
# Imperative - exact steps of how to make infra 
# Declarative - Predefined of how infra should me made, need to specify the configuration
# With terrafrom you declare the resources you want made with which configuration and let terraform decide the process in which those resources are made as apposed to definig each step of the process as with an imperative aappraoch 
- Idempotenet and Consitent 
# Idempotenet - the defined config matchein the terraform matches the exisiting infra
# Checks terraform against state file - if you havent changed anything about your config and you apply it again to the same environment, nothing will change in the environment as your defined config matches the reality of the infra that exists  
- Push or Pull 
# Terraform is a push type model - the config that terraform has is getting pushed to the target environment 

Benefits 
- Reuable components 
- Automated deployment (tf jobs)
- Repeatable Process (Creation and maintenance of infra is repeatable and consistent, each time you need to build out or update an environmet you simply need to update and apply the configuration)
- Consistent envirnoments 
- Documneted Architeture - deeper understanding of archituture 

IaC - sourcce of truth for infra configuration 
Manual processes are the enemy - relying on manual processes to deploy environments consistenly in a repeatable fashion, at some point a step is going to be missed 

What is Terraform?
Tool used to automate infrastrucutre 
Tool to automate the deployment and managment of infrasturucture 
Vendor agnostic - any service with an API 
Written in HCL - HashipCorp COnfiguration Language 
Declarative Syntax 
Push style of deployment to create infra - terraform reaches out to any given API and tells it which infra to create
Provider Plugin architure to interact with various cloud providers and servies 
COnfig written in HCL or JSON
Basic workflow: init, plan, apply, destroy


Core Components of Terraform  
- executable 
- Configuration files 
- Provider Plugins
- State data 
# Current information about your deployment, mapping of the infra defined in your config to what exists in your target environment
# When you want to do an update of your environment - tf compares your updated config to what's in the state file, calulates the changes to make the state file match the updated config, makes the changes in the target environment and then updates the state file 

Terraform object types 
- Providers 
# Define information about a provider plug in you want to use - for example with AWS provider - wants to know AWS creditails and region 
- Resources 
# Things being reated in a target envirnoment - associated with a provider and will require additional info for confi eg EC2
- Data  
# A way to query infor from a provider - asking for info that might be used in the config - read only/ Eg. Availability zones, AMI list   
- Variables 
# vars used instead of hard coding variables to increase resuability 
- Locals
# Computed inside the config, cannot input directly into them. Useful for values with muliple references, helps with data transformation 
- Outputs 


Terraform workflow 
- terraform innit
# looks through config inside current working directory for provider plugins. Unless specififed elsewhere will look to download from the public terraform registry 
# Terraform needs to store state data aboout your config. During init state backend is created. Unless backend is specififed tf will create a state data file in the cwd
# Once init is complete - tf is ready to deploy some infra  

- terraform plan 
# tf will look at current config and state data, and determine the differences between the two and make a plan to update the target environment to match the desired config. Tf will print out the plan for you to look at and verify the changes terraform wants to make 

- terraform apply
# applies the infrasturucture changes outlined in the plan

- terraform destroy 
# delete everything in the infra based on what is in the state data - useful for deleting a whole project 

Syntax 
- terraform fmt 
# formatting code 
# fmt -check - outputs files requireing changes, does not carry out changes 
# fmt -recursive - applies formatting across nested directories  
- terraform validate
# validates formatting - checks code logic 
# needs to be run after terraform init, to check config 

