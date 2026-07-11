pipeline {
    agent any

    stages {

        stage('Checkout Code') {
            steps {
                echo 'Checking out code from GitHub...'
                checkout scm
            }
        }

        stage('Run Tests') {
            steps {
                echo 'Running Python unit tests...'
                sh 'python3 -m unittest test_app.py'
            }
        }

        stage('Run Application') {
            steps {
                echo 'Running Python application...'
                sh 'python3 app.py'
            }
        }
    }

    post {
        success {
            echo 'Build completed successfully!'
        }
        failure {
            echo 'Build failed!'
        }
        always {
            echo 'Pipeline execution finished.'
        }
    }
}
