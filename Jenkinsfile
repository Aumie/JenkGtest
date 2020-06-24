pipeline {
    agent { docker{image 'rikorose/gcc-cmake'} }
    stages {
        stage('build') {
            steps {
                    sh 'pwd'
                    dir('build'){
                        sh 'pwd'
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