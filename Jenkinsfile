pipeline {
    agent any

    stages {
	
        stage('CLONE SCM STAGE') {
            steps {
                echo 'Cloning code from Git Hub'
				git branch: 'main', credentialsId: 'github', url: 'https://github.com/Sushmitha31/Sushmitha.git'
            }
        }
		
        stage('BUILD ARTIFACT STAGE') {
            steps {
                echo 'show the code'
				sh 'ls'
				echo 'build using maven'
				sh 'mvn clean install'
				
            }
        }
		
        stage('DEPLY TO TOMCAT STAGE') {
            steps {
                echo 'deploy to tomcat application server'
				deploy adapters: [tomcat9(credentialsId: 'tomcat', path: '', url: 'http://3.84.168.15:8090/')], contextPath: 'FACEBOOK', war: '**/*.war'
				
            }
        }
		
    }
}
