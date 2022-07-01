node {
     checkout scm   
    stage ('Cleaning Local Images and Containers') {
                 sh 'docker stop $(docker ps -a -q) || true && docker rm $(docker ps -a -q) || true && docker rmi -f $(docker images -a -q) || true'
     }
    stage('docker-compose build ') {
                 sh 'docker-compose build && docker-compose up -d'
    }
    stage('docker containers testing') {
                 sh 'wget localhost:5001 && wget localhost:3308' 
    }   
    stage('docker images  push') {
        withCredentials([usernamePassword(credentialsId: 'dockerHub', passwordVariable: 'DOCKERHUB_CREDENTIALS_PSW', usernameVariable: 'DOCKERHUB_CREDENTIALS_USR')]) {
                sh 'docker push dhivyadhub/pythonapp:1 && docker push dhivyadhub/sqlapp:1'
               } 
    }     
}
