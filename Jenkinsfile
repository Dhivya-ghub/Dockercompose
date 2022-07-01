node {
     checkout scm   
    stage ('Cleaning Local Images and Containers') {
                 sh 'docker stop $(docker ps -a -q) || true && docker rm $(docker ps -a -q) || true && docker rmi -f $(docker images -a -q) || true'
     }
    stage('docker-compose build ') {
                 sh 'docker-compose build && docker-compose up -d'
    }
    stage('docker push') {
        withCredentials([usernamePassword(credentialsId: 'dockerHub', passwordVariable: 'DOCKERHUB_CREDENTIALS_PSW', usernameVariable: 'DOCKERHUB_CREDENTIALS_USR')]) {
                sh 'docker push pythonapp:1'
               } 
    }     
    stage('docker-compose down') {
                 sh 'docker-compose down'
    }     
}
