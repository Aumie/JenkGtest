pipeline {
    agent { docker{image 'gcc'} }
    stages {
        stage('build') {
            steps {
                    sh 'pwd'
                    dir('cmake-*'){
                        sh 'pwd'
                        sh 'make clean'
                        sh 'make all'
                    }
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