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
                    ./hello_exec  # Restore correct command
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
