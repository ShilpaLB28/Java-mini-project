pipeline {
    agent {
        label 'slave'
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