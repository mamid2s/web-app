node('docker'){
  stage('Package') {
    checkout scm
  }
  stage('Deploy App') {
    sh "docker-compose up"
  } 
}
