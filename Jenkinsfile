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
		deploy adapters: [tomcat9(alternativeDeploymentContext: '', credentialsId: 'fe9df3e4-cf1b-4e86-81b2-a06195817cc3', path: '', url: 'http://192.11.15.17:8282/')], contextPath: 'Maven web App', war: '**/*.war'
			
		}
	}

	}
}
