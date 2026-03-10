pipeline {

    agent any

    tools {
        maven 'Maven'
        jdk 'JDK 25'
    }

    stages {

        stage('Checkout') {
            steps {
             git branch: 'main',url: 'https://github.com/soumadipchangder/Jenkins_1stproject'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean compile'
            }
         
         
        }

        stage('Run JUnit Tests') {
            steps {
                sh 'mvn test'
            }
        }

       stage('SonarQube Analysis') {
          steps {
          withSonarQubeEnv('SonarServer') {
            sh 'mvn clean verify sonar:sonar'
        }
    }
}

    }
}