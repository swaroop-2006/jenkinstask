pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                echo 'Fetching latest code from GitHub'
                checkout scm
            }
        }

        stage('Build') {
            steps {
                echo 'Static website - no build required'
            }
        }

        stage('Test') {
            steps {
                sh 'test -f index.html'
                sh 'test -f style.css'
                sh 'test -f script.js'
            }
        }

    }

    post {
        success {
            echo 'Website deployed successfully'
        }

        failure {
            echo 'Pipeline failed'
        }
    }
}