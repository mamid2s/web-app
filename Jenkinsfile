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
      echo "My Branch Name: ${env.BRANCH_NAME}"
      script {
        def myLib = new smacademy.git.gitStuff();
        echo "My Commit: ${myLib.gitCommit("${env.WORKSPACE}/.git")}"
      }
  }
  stage('Deploy App') {
    sh "docker-compose up"
  }
}
