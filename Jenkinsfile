node {
    stage ('Cleaning Local Images and Containers') {
               sh 'docker stop $(docker ps -a -q) || true && docker rm $(docker ps -a -q) || true && docker rmi -f $(docker images -a -q) || true'
    }
    stage('docker-compose') {
                 sh "sudo docker-compose up --build -d"
    }    
}
