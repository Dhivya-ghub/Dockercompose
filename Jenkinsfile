pipeline {
    agent any
    environment {
	registry = "dhivyadhub/dockercompose" 
        registryCredential = 'dockerhub_id'
	dockerImage = ''    
	}
    stages {
        stage('git clone') {
            steps {
                // Get code from a GitHub repository
                git url: 'https://github.com/Dhivya-ghub/Dockercompose.git', branch: 'feature',
                 credentialsId: 'github_creds'
            }
	}   
        stage('Building our image') { 
            steps { 
                script { 
                    dockerImage = docker.build registry + ":$BUILD_NUMBER" 
                }
            } 
        }
        stage('Deploy our image') { 
            steps { 
                script { 
                    docker.withRegistry( '', registryCredential ) { 
                        dockerImage.push() 
                    }
                } 
            }
        } 
        stage('Cleaning up') { 
            steps {

                bat "docker rmi $registry:$BUILD_NUMBER" 
            }
        } 
    }
 }
