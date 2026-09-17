pipeline {
    agent any

    stages {

        stage('Cloner le projet') {
            steps {
                checkout scm
            }
        }

        stage('Tester') {
            steps {
                sh 'python3 --version'
                sh 'python3 app.py'
            }
        }

        stage('Construire Docker') {
            steps {
                sh 'docker build -t devops-demo:latest .'
            }
        }

        stage('Lancer Docker') {
            steps {
                sh 'docker run --rm devops-demo:latest'
            }
        }
    }
}
