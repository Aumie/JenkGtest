pipeline {
    agent { docker{image 'ubuntu:20.04'} }
    stages {
        stage('build') {
            steps {
                    sh 'cd cmake*'
                    sh 'make all'
                    sh 'cd ..'
                }
            }
        stage('test') {
            steps {
                    sh './cmake-build-debug/tst/ExampleProject_tst'
                }
            }
    }
    post{
        success {
            echo 'successful'
        }
        failure {
            echo 'failed'
        }
    }
}