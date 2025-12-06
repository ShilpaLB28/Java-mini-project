pipeline {
    agent any
    tools { 
        jdk 'jdk17'
        maven 'maven3'
    }
    stages {
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
            archiveArtifacts artifacts: '**/target/*.war'
        }
    }
}
