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
				bat 'docker build -t dhivyadhub/dockercompose::$BUILD_NUMBER .'
			}
		}
    }
}