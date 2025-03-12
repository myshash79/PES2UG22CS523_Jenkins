pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh '''
                    cd main
                    ls -l
                    g++ hello.cpp -o hello_exec
                '''
            }
        }
        
        stage('Test') {
            steps {
                sh '''
                    cd main
                    ./invalid_exec  # This file does not exist, so it will fail
                '''
            }
        }
        
        stage('Deploy') {
            steps {
                echo 'Deploying Application...'
            }
        }
    }
    
    post {
        failure {
            echo 'Pipeline Failed!'
        }
    }
}
