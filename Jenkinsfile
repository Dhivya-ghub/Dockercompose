node {
    environment {
        registry = "dhivyadhub/dockercompose"     
    }
    stage ('Cleaning Local Images and Containers') {
           steps {
               sh 'docker stop $(docker ps -a -q) || true && docker rm $(docker ps -a -q) || true && docker rmi -f $(docker images -a -q) || true'
           }
    stage('docker-compose') {
                 sh "docker-compose build && docker-compose up -d"
    }    
}
