pipeline {
    agent { docker{image 'ubuntu:20.04'} }
    stages {
        stage('set up') {
            steps {
                    sh 'sudo apt-get install build-essential'
                }
            }
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