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

	stage('Build to War file'){
		steps{
		sh "mvn clean install"
		}
	}

	stage('Deploy to tomcat Container'){
		steps{
		deploy adapters: [tomcat9(alternativeDeploymentContext: '', credentialsId: 'f5c28479-1e5c-4f04-a325-82453c9eacf7', path: '', url: 'http://192.11.15.17:8282/')], contextPath: 'maven-web-app', war: '**/*.war'

		}
	}

	}
}
