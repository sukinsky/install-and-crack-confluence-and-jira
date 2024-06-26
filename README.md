# Setup Confluence and Jira with PostgreSQL

## Dependencies:

### Install Taskfile
* [taskfile](https://taskfile.dev/installation/)

### install docker
* [docker installation](https://docs.docker.com/get-docker/)

### install git
* [git installation](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)

### download **attlassian-agent-use-in-JAVA_OPTS.jar** and **atlassian-agent-license-generator.jar**
* [Licence Generator](https://drive.google.com/drive/folders/1QJzVjndzT0kQJkY74M2Oo0cRPGNb38TE?usp=sharing)

### clone repository
    git clone https://github.com/sukinsky/install-and-crack-confluence-and-jira.git

### Your directory should have the following files
--> Dockerfile
<br/>
--> Dockerfile-jira
<br/>
--> docker-compose.yml
<br/>
--> Taskfile.yml
<br/>
--> atlassian-agent-use-in-JAVA_OPTS.jar
<br/>
--> atlassian-agent-license-generator.jar
<br/><br/>

# Use the following commands to launch and crack Confluence:

## Run Dockerfile
    task build
    task buildjira

## up docker compose file 
    task up

## Generating a license for your Confluence server. please Copy the generated code and paste it on the start page
    task gen -- "input serverID"

## Generating a license for your Jira server. please Copy the generated code and paste it on the start page
    task genjira -- "input serverID"

## If you have installed a plugin on confluence, you can use the following command to generate a license
    task plugin -- "input plugin app key"

# If needed, you can also use the following commands

## push your image to image registery (optional)
    task push

## down docker compose file (optional)
    task down
# Usable info for new installations
## Watcher field
The old plugin is notworking with Jira 9.x but there is a fork with corrected version
    https://community.atlassian.com/t5/Jira-Software-questions/Is-there-an-alternative-to-burningcode-s-now-defunct-Jira/qaq-p/1779262
    https://bitbucket.org/superoni/jira-watcher-field-plugin/downloads/
