pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                // Get code from a GitHub repository
                git url: 'https://github.com/Dhivya-ghub/Dockercompose.git', branch: 'feature',
                 credentialsId: 'github_creds'
            }
        }
    }
}