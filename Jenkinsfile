
pipeline {
    agent { docker{image 'ubuntu:20.04'} }
    stages {
        stage('set up') {
            steps {
                    sh 'apt-get update'
                    sh 'apt-get install cmake'
                    sh 'apt-get install make'
                }
            }
        stage('build') {
            steps {
                    dir(build){
                        sh 'make all'
                    }
                }
            }
        stage('test') {
            steps {
                    sh './build/tst/ExampleProject_tst'
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