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
                 sh 'docker build -t mon_app:latest .'
                sh 'docker run -d -p 8080:80 mon_app:latest'
            }
        }
    }
     post {
        success {
            // Envoyez des notifications en cas de succès (par exemple, Slack, e-mail)
            echo 'Pipeline réussi !'
        }
        failure {
            // Envoyez des notifications en cas d'échec (par exemple, Slack, e-mail)
            echo 'Le pipeline a échoué.'
        }
    }
}
