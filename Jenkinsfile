pipeline {
  agent any

  stages {

    stage ('Build') {
      steps {
        sh 'sudo docker build -t jenkins .'
        sh 'sudo docker tag jenkins alibekdariger/fastapi:latest'
      }
    }

    stage ('Push'){
      steps{
        sh 'sudo docker push alibekdariger/fastapi:latest'
      }
    }

    stage ('deploy'){
      steps{
        sh 'sudo docker run -d --name jenkins -p 8000:8000 alibekdariger/fastapi:latest'
      }
    }
  }
}
