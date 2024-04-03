pipeline {
	agent any
    parameters {
		choice(name: 'DEPLOY_TO', choices: ['DEV', 'QA', 'PROD'])
	} 	
	stages {
		stage('Checkout') {
			steps {
				echo 'Checkout completed'
			}
		}
		stage('Static-test') {
			steps {
				echo 'Running static tests on code'
			}
		}
		stage('Build') {
			when {
				branch "main"				
			}
			steps {
				sh 'echo "Building the code"'
			}
		}
		stage('Deploy') {
			when {
				environment name: 'DEPLOY_TO', value: 'PROD'
			}
			steps {
				echo 'Deploying into environment'
			}
		}
	}
}
