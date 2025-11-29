pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                echo 'Récupération du code depuis Git...'
            }
        }

        stage('Build / Test') {
            steps {
                echo 'Execution du script Python...'
                sh 'python3 app.py'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Simulation du déploiement...'
                sh 'mkdir -p /tmp/deploy && cp -r * /tmp/deploy/'
            }
        }
    }

    post {
        success {
            echo 'Pipeline terminé avec succès !'
        }
        failure {
            echo 'Erreur dans le pipeline !'
        }
    }
}
