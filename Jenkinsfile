pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build') {
            steps {
                sh 'python -m pip install -r requirements.txt'
            }
        }

        stage('Test') {
            steps {
                sh 'python -m unittest discover tests'
            }
        }

        stage('Deploy') {
            steps {
                // Déployer votre application ici (par exemple, via Docker)
            }
        }
    }
}
