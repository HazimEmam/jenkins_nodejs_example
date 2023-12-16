pipeline {
    agent any

    environment {
        PATH = "/usr/bin:/bin:/usr/local/bin:/usr/local/sbin:/usr/sbin:${tool 'NodeJS'}/bin"
    }

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Install Dependencies') {
            steps {
                sh 'npm install'
            }
        }

        stage('Run Tests') {
            steps {
                sh 'npm test'
            }
        }
    }

    post {
        success {
            echo 'CI Pipeline succeeded!'
        }
        failure {
            echo 'CI Pipeline failed!'
        }
    }
}
