pipeline {
    agent { docker{image 'gcc'} }
    stages {
        stage('build') {
            steps {
                    sh 'pwd'
                    dir('build'){
                        sh 'pwd'
                        sh 'cmake .. -DCMAKE_BUILD_TYPE=Debug -G "Unix Makefiles"'
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