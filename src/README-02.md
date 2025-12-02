# Jenkins Declarative Pipeline
- Purpose: Designed to be simpler and more readable.
- Structure: Predefined structure with specific sections

For Example:
```
pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Building...'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing...'
            }
        }
    }
}
```

**Pros:**
- Easier to write and read
- Built-in error handling
- Good for teams and shared environments
- Enforces structure and consistency

**Cons:**
- Less flexible for complex logic

## Declarative vs Scripted
| Feature     | Declarative	| Scripted | 
|--------------|-------------|---------|
|Syntax|Groovy Structured DSL (predefined syntax)| Raw Groovy code script|
|Readability|High| Medium/Low|
|Flexibility	|Strict, structured syntax|Flexible, more open syntax|
|Error Handling	|Built-in|Manual,Requires Groovy programming knowledge|
|Use Case|Common pipelines|Complex logic|



## Lab - Create pipeline based on Jenkinsfile
- copy the below script to public repo
- set SCM = GIT
- Repository URL = make sure the url of jenkinsfile is **under public repo**
- make sure that you branch of jenkinsfile is correct
- Execute the  pipeline of Jenkinsfile

```
pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
        stage('Security') {
            steps {
                echo 'Security....gm gm gm'
            }
        }
    }
}

```
- **Install plugin stage view** go to Dashboard -> Manage Jenkins -> Plugins -> Availiable plugins
- for plugin page, go to slash **manage**
```
http://host-ip:8080/manage/
    # After Restart jenkins service, start docker container if needed
docker start <container id>
```
