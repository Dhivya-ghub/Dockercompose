node {
    environment {
        registry = "dhivyadhub/dockercompose"     
    }
    stage('git clone') {
                // Get code from a GitHub repository
                git url: 'https://github.com/Dhivya-ghub/Dockercompose.git', branch: 'feature',
                 credentialsId: 'github_creds'
    } 
    stage('docker-compose') {
                 bat "docker-compose build && docker-compose up -d"
    }    
}
