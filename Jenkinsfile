pipeline {
    agent {
        label 'slave'
    }
    tools { 
        jdk 'jdk17'
        maven 'maven3'
    }
    stages {
        stage('Build') {
            steps {
                dir('sample-app')
                sh 'mvn clean install'
            }
            post {
                success {
                    archiveartifacts artifacts: '**/target/*.war'
                }
            }
        }
    }
}