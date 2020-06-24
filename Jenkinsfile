pipeline {
    agent { docker{image 'gcc'} }
    stages {
        stage('build') {
            steps {
                    sh 'pwd'
                    dir('cmake-build-debug'){
                        sh 'pwd'
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