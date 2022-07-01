node {
     checkout scm   
    stage('docker-compose build ') {
                 sh 'docker-compose build && docker-compose up -d'
    }
    stage('docker-compose down') {
                 sh 'docker-compose down'
    }     
}
