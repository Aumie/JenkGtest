pipeline {
    agent { docker{image 'gcc'} }
    stages {
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