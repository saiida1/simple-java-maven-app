pipeline {
  agent {
    docker {
      image 'maven:3-alpine'
    }
    
  }
  stages {
    stage('Build') {
      steps {
        powershell 'mvn -B -DskipTests clean package'
      }
    }
    stage('Test') {
      steps {
        powershell 'mvn test'
      }
    }
    stage('Deliver') {
      steps {
        powershell './jenkins/scripts/deliver.sh'
      }
    }
  }
}