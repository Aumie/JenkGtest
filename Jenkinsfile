pipeline {
    agent { docker{image 'gcc'} }
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
                    sh 'make Makefile'
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