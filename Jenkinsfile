pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        echo 'Building..'
        sh 'mvn compile'
      }
    }

    stage('Test') {
      steps {
        echo 'Test Pass...'
        sh 'mvn test'
      }
    }

    stage('Package') {
      steps {
        echo 'Packaging....'
        sh 'mvn clean package -DskipTest'
        archiveArtifacts(artifacts: '**/target/*.jar', fingerprint: true)
      }
    }

  }
  tools {
    maven 'maven 3.9.3'
  }
}