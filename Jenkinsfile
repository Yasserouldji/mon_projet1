pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Install dependencies') {
            steps {
                sh '''
                    python3 -m venv venv
                    . venv/bin/activate
                    pip install --upgrade pip
                    pip install pytest
                '''
            }
        }

        stage('Run Tests') {
            steps {
                sh '''
                    . venv/bin/activate
                    pytest -q --disable-warnings --maxfail=1
                '''
            }
        }

        stage('Webhook Test') {
            steps {
                echo "🎉 Webhook OK ! Le build a été déclenché automatiquement depuis GitHub."
                sh 'echo "Test webhook : build déclenché !!!!"'
            }
        }

    }

    post {
        always {
            echo "Pipeline terminé."
        }
    }
}

