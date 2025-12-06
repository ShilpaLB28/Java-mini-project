pipeline {
    agent any
    parameters {
        string defaultValue: 'L B', name: 'LastName'
        }

    environment {
        NAME = "shilpa"
    }
    tools { 
        jdk 'jdk17'
        maven 'maven3'
    }
    stages {
        stage('Build') {
            steps {
                dir('sample-app') {
                    sh 'mvn clean install'
                    echo "hello $NAME ${params.LastName}"
                }
            }
        }
        stage('test') {
            parallel {
                stage('test A') {
                    steps {
                        echo "test a"
                    }
                }
                stage('test B') {
                    steps {
                        echo "test b"
                    }
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
