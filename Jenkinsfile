pipeline {
  agent any

  stages {

    stage ('Build') {
      steps {
        sh 'docker build -t jenkins .'
        sh 'docker tag jenkins alibekdariger/fastapi:latest'
      }
    }

    stage ('Push'){
      steps{
        sh 'docker push alibekdariger/fastapi:latest'
      }
    }

    stage ('deploy'){
      steps{
        sh 'docker run -d --name jenkins -p 8000:8000 alibekdariger/fastapi:latest'
      }
    }
  }
}
