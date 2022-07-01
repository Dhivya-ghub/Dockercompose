node {
     checkout scm   
    stage('docker-compose build ') {
                 sh 'docker-compose build && docker-compose up -d'
    }
    stage('docker push') {
        withCredentials([usernamePassword(credentialsId: 'dockerHub', passwordVariable: 'DOCKERHUB_CREDENTIALS_PSW', usernameVariable: 'DOCKERHUB_CREDENTIALS_USR')]) {
                sh 'docker push dockerdhub/pythonapp:$BUILD_NUMBER'
               } 
    stage('docker-compose down') {
                 sh 'docker-compose down'
    }     
}
