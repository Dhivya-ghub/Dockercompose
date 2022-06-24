pipeline {
    agent any
    environment {
		DOCKERHUB_CREDENTIALS=credentials('dockerhub')
	}
    stages {
        stage('git clone') {
            steps {
                // Get code from a GitHub repository
                git url: 'https://github.com/Dhivya-ghub/Dockercompose.git', branch: 'feature',
                 credentialsId: 'github_creds'
            }
	}   
        stage('Build') {

			steps {
				bat 'docker build -t dhivyadhub/dockercompose::%BUILD_NUMBER% .'
			}
		}

		stage('Login') {

			steps {
				bat 'echo $DOCKERHUB_CREDENTIALS_PSW | docker login -u $DOCKERHUB_CREDENTIALS_USR --password-stdin'
			}
		}

		stage('Push') {

			steps {
				bat 'docker push dhivyadhub/dockercompose::%BUILD_NUMBER%'
			}
		}
	}

	post {
		always {
			bat 'docker logout'
		}
	}
    }
