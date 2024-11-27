pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        script {
          bat 'dotnet build microservicesTest.sln'
        }
      }
    }
    stage('Docker Build') {
      steps {
        script {
          bat 'docker build -t microservicestest-api.'
        }
      }
    }
    stage('Deploy to Staging') {
      steps {
        script {
          bat 'docker-compose up --build -d'
        }
      }
    }
  }
}