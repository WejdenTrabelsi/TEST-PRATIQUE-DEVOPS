pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                echo 'Récupérer le code du dépôt Git'
                git branch: 'main', url: 'https://github.com/WejdenTrabelsi/TEST-PRATIQUE-DEVOPS.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                echo 'Install dépendances Node'
                sh 'npm install'
            }
        }

        stage('Run Tests') {
            steps {
                echo 'Exécution des tests'
                sh 'npm test'
            }
        }

        stage('Build Docker Image') {
            steps {
                echo 'Construction de l\'image Docker'
                sh 'docker build -t todo-app .'
            }
        }
    }

    post {
        success {
            echo 'Pipeline exécuté avec success !'
        }
        failure {
            echo 'La pipeline failed'
        }
    }
}
