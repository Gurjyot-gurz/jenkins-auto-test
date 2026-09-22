pipeline {
    agent any

    stages {

        stage('Checkout Code') {
            steps {
                checkout scm
            }
        }

        stage('Install Dependencies') {
            steps {
                bat 'py -m pip install -r requirements.txt'
            }
        }

        stage('Run Automated Tests') {
            steps {
                bat 'py -m pytest -v'
            }
        }
    }

    post {
        success {
            echo 'All tests passed!'
        }

        failure {
            echo 'Build or tests failed!'
        }
    }
}
