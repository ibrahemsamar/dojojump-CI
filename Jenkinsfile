pipeline{

	agent any

	environment {
		DOCKERHUB_CREDENTIALS=credentials('samarHACATHONSDACODINGDOJO')
	}

	stages {

		stage('Build') {

			steps {
				sh 'docker build -t songosh54/dojo-jump-game:latest .'
			}
		}

		stage('Login') {

			steps {
				sh 'echo $DOCKERHUB_CREDENTIALS_PSW | docker login -u $DOCKERHUB_CREDENTIALS_USR --password-stdin'
			}
		}

		stage('Push') {

			steps {
				sh 'docker push chandradeoarya/dojo-jump:latest'
			}
		}
	}

	post {
		always {
			sh 'docker logout'
		}
	}

}