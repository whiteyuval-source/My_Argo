# Jenkins - Connect and set the server
- connect via ssh and add user and folder if needed

```
 useradd or adduser - You can add a new user in Linux using the useradd or adduser command​
 For Example:  sudo useradd -m -s /bin/bash sela
-m: Create a home directory (/home/sela)​
-s /bin/bash: Set default shell​
  # Create a dir if not exist
cd home/
sudo mkdir gm
sudo chmod 777 gm
```

# Continuous Integration (CI)
Continuous Integration (CI) is a DevOps practice where developers regularly merge their code changes into a shared repository, and automated builds and tests are run to verify those changes

![Alt text](pic-gh-ci.png)

**Continuous integration / delivery, deployment**
- **Continuous integration** is refers to the build and unit testing stages of the software release process 
  Every revision that is committed triggers an automated build and test
- **Continuous Delivery** is the code is always releasable by release manager ​
It can't go to the next stage until approval by release manager ​
The release manager is such a Gate Keeper​
- **Continuous Deployment** is take the Continuous Delivery one step further​
whenever the developer committee code, after successful automatic testing it is deploy into production environment​
The process required high level confident on automatic pipeline ​
Team can response faster ​

## **Jenkins installation base on Docker image**
- Work local server - PreRequsite is Docker desktop installed

```
docker run -d --name jenkins -p 8080:8080 jenkins/jenkins
  # See the logs in case its not work, see the solution in repo ci-cd
docker logs <container id>
sudo curl ifconfig.me
```
- Go to the browser and open a new tab http://host-ip:8080
### in docker cli run the below command and insert to the jenkins password page

```
docker logs jenkins
  # other option to generate password
docker exec jenkins cat /var/jenkins_home/secrets/initialAdminPassword
```



```
http://<Infrastructure-Server-Ip>:8080
  # Generate the password
docker exec jenkins cat /var/jenkins_home/secrets/initialAdminPassword
```
- log in as:
  - user=admin
  - password=admin

### Freestyle job
A Jenkins Freestyle job is a basic project type in Jenkins that allows you to run simple build, test, and deploy tasks. It is a good starting point for beginners to understand Jenkins automation



#### Lab - Freestyle job

- Go to the **New Item** and choose **Freestyle project**
  Go to Build Steps -> Execute shell -> and type
```
echo "My first Freestyle job"
```
- Run the job
For more options:
- Build Triggers
    -  Example: check "Poll SCM" and enter H/5 * * * * to poll every 5 minutes

- Build Environment
    - Choose Delete workspace before build starts


### Jenkins Declarative and Scripted pipelines
In Jenkins, Declarative and Scripted pipelines are two different syntaxes used to define Continuous Integration/Delivery (CI/CD) workflows

#### Scripted Pipeline
- Purpose: Offers full control and flexibility using Groovy
  
**Pros:**
  
  - Powerful and flexible.
  - Ideal for complex use cases or logic.
  - More like traditional programming

**Cons:**

  - Harder to maintain and read.
  - No built-in error handling structure


#### Lab - Scripted Pipeline
- Go to the **New Item** and choose name of **pipieline script**
- In Definition choose Pipeline script as below 


![Alt text](pipeline-script.png)

- Save and run the job

##### Bounos lab
- Generate via groovy **sleep time** module and add it to **Scripted Pipeline**
