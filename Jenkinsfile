pipeline {
    agent any
    environment {
<<<<<<< HEAD
		DOCKERHUB_CREDENTIALS=credentials('dockerhub')
=======
	registry = "dhivyadhub/dockercompose" 
        registryCredential = 'dockerhub_id'
	dockerImage = ''    
>>>>>>> 9076703c492a28dbc4b56faf3382f5df2fbcee83
	}
    stages {
        stage('git clone') {
            steps {
                // Get code from a GitHub repository
                git url: 'https://github.com/Dhivya-ghub/Dockercompose.git', branch: 'feature',
                 credentialsId: 'github_creds'
            }
<<<<<<< HEAD
        }
        stage('Build') {

			steps {
				bat 'docker build -t dhivyadhub/dockercompose::$BUILD_NUMBER .'
			}
		}
    }
=======
	    }   
        stage('Build') {

			steps {
				bat 'docker build -t dhivyadhub/dockercompose:%BUILD_NUMBER% .'
			}
		}

		stage('Login') {

			steps {
				bat 'echo $DOCKERHUB_CREDENTIALS_PSW | docker login -u $DOCKERHUB_CREDENTIALS_USR --password-stdin'
			}
		}

		stage('Push') {

			steps {
				bat 'docker push dhivyadhub/dockercompose:%BUILD_NUMBER%'
			}
		}
	}
>>>>>>> 9076703c492a28dbc4b56faf3382f5df2fbcee83
}