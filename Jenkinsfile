pipeline {
agent any




stages {
    stage('Clone') {
        steps {
            // Clonage via SSH avec la credential configurée dans Jenkins
            git branch: 'main',
                url: 'git@github.com:Yasserouldji/mon_projet1.git',
                credentialsId: 'GitHub-SSH'  // <-- Met l'ID de ta credential SSH ici
        }
    }

    stage('Install dependencies') {
    steps {
        sh 'pip3 install -r requirements.txt'
    }
}


    stage('Run app') {
        steps {
            sh 'python app.py'
        }
    }

    stage('Tests') {
        steps {
            // Si tu as des tests unitaires, tu peux les lancer ici
            sh 'echo "Tests placeholder"'
        }
    }
}

post {
    success {
        echo 'Pipeline terminé avec succès !'
    }
    failure {
        echo 'Le pipeline a échoué.'
    }
}


}
