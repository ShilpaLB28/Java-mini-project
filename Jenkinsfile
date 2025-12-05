pipeline {
    agent {
        label 'slave'
    }
    stages {
        stage('Build') {
            steps {
                echo "build step"
            }
        }
        stage('test') {
            steps {
                echo "test stage"
            }
        }
        stage('deploy') {
            steps {
                echo "deploy stage"
            }
        }
    }
}