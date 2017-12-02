node('docker'){
  stage('Package') {
    checkout scm
  }
  stage('Build Image') {
    sh "docker build -t web-app:latest -f Dockerfile ."
  }
  stage(Say Hello){
    agent any
    
    steps {
      sayHello 'A'
    }
    
  }
  stage('Deploy App') {
    sh "docker-compose up"
  } 
}






