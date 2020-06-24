pipeline {
    agent { label : 'master' }
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