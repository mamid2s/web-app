node('docker'){
  stage('Package') {
    checkout scm
  }
  stage('Build Image') {
    sh "docker build -t web-app:latest -f Dockerfile ."
  }
  stage('Say Hello'){
    sayHello ('Sandy');
  }
  stage('Git Information'){
    steps {
      echo "My Branch Name: ${env.BRANCH_NAME}"
      script {
        def myLib = new linuxacademy.git.gitStuff();
        echo "My Commit: ${myLib("${env.WORKSPACE}/.git")}"
      }
    }
  }
  stage('Deploy App') {
    sh "docker-compose up"
  }
}
