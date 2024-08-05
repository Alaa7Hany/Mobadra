pipeline {
	agent any

	stages {
		stage('build') {
			steps {
				sh 'docker build -t jenkins-pet .'
			}
		}
		stage('deploy') {
			steps {
				sh 'sudo docker compose up -d'
			}
		}
	}
}