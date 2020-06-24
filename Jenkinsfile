pipeline {
    agent { docker{image 'gcc'} }
    stages {
        stage('build') {
            steps {
                    sh 'cd cmake*'
                    sh 'pwd'
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