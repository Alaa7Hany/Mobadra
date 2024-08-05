pipeline {
	agent any

	stages {
		stage('build') {
			steps {
				sh 'sudo docker build -t jenkins-pet .'
				echo "#####build#####"
			}
		}
		stage('deploy') {
			steps {
				echo "####deploy####"
				sh '''
					sudo docker compose up -d
					sudo sleep 20
					'''
			}
		}
	}
}
