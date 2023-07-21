pipeline {
    agent any

    tools {
      maven 'maven 3.9.3'
     }

    stages {
        
         stage('SCM-Checkout') {
            steps {
                echo 'SCM-Checkout..'
              git 'https://github.com/school-of-devops-val/carts.git'
            }
        }
        
        
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
                archiveArtifacts artifacts: '**/target/*.jar', fingerprint: true
            }
        }
    }
}
