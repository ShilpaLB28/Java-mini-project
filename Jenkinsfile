pipeline {
    agent {
        label 'slave'
    }
    tools { 
        jdk 'jdk17'
        maven 'maven3'
    }
    stages {
        stage('checkout') {
            steps {
                git branch: 'main',
                url: 'https://github.com/panchami30/Java-mini-project.git',
                credentialsID: 'git'
            }
        }
        stage('Build') {
            steps {
                dir('sample-app') {
                    sh 'mvn clean install'
                }
            }
        }
    }
    post {
        success {
            archiveartifacts artifacts: '**/target/*.war'
        }
    }
}