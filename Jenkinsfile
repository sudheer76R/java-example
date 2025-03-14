pipeline {
    agent { label 'maven-agent' }
	
    tools {
        maven 'maven'
    }

	environment {
        tomcat_webapps = "/root/tomcat/webapps"
    }

    stages {
        stage('Checkout Code') {
            steps {
                git branch: 'feature-branch', credentialsId: 'github', url: 'https://github.com/bhagyashreep032/jenkins-java-example.git'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }

        stage('Deploy') {
            steps {
                sh 'sudo cp target/*.war $tomcat_webapps'
            }
        }
    }
}
