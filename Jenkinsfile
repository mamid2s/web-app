@Library('jenkins-pipeline-libs@develop') _
sayHello()
node('docker'){
  stage('Package') {
    checkout scm
  }
  stage('Build Image') {
    sh "docker build -t web-app:latest -f Dockerfile ."
  }
  stage('Deploy App') {
    sh "docker-compose up"
  } 
}






