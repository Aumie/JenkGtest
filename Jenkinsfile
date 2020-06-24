pipeline {
    agent { docker{image 'ubuntu:20.04'} }
    stages {
        stage('set up') {
            steps {
                    sh 'apt-get update'
                    sh 'apt-get install make'
                }
            }
        stage('build') {
            steps {
                    sh 'cd cmake*'
                    sh 'make'
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