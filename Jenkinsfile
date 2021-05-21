pipeline {
    agent any
    tools{
	maven 'Maven 3.8.1'
	}
    stages {
        stage("clone code"){
            steps{
               git credentialsId: 'git_credentials', url: 'https://github.com/Devakumar124/jenkinsdeploy.git'
            }
        }
        stage("build code"){
            steps{
              sh "mvn clean install"
            }
        }
        stage("deploy"){
            steps{
              deploy adapters: [tomcat9(credentialsId: 'f504a826-18c6-406d-8700-eb0df01368a9', path: '', url: 'http://13.233.97.26:8080')], contextPath: 'one', war: '**/*.war'
                 
                }
            }
        }
    
}
