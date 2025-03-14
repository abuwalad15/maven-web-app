pipeline {
	agent any
	tools{
        maven 'maven-3.9.9'
    	}
	stages{
		stage('Checkout Code'){
			steps{
				checkout scm
				}
			}

	stage('Build'){
		steps{
		sh "mvn clean install"
		}
	}

	stage('Deployment'){
		steps{
		deploy adapters: [tomcat9(credentialsId: 'e03d3314-895c-4135-a5cc-3a4fe4caa3e8', path: '', url: 'http://192.11.15.124:8080/')], contextPath: null, war: 'target/*.war'
		}
	}

	}
}
