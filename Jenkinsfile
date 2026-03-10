pipeline {

    agent any

    tools {
        maven 'Maven'
        jdk 'JDK25'
    }

    stages {

        stage('Checkout') {
            steps {
             git branch: 'main',url: 'https://github.com/soumadipchangder/Jenkins_1stproject'
            }
        }

        stage('Build') {
            steps {
                bat 'mvn clean compile'
            }
         
         
        }

        stage('Run JUnit Tests') {
            steps {
                bat 'mvn test'
            }
        }

       stage('SonarQube Analysis') {
          steps {
          withSonarQubeEnv('SonarServer') {
            bat 'mvn clean verify sonar:sonar'
        }
    }
}

    }
}