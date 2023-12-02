pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Instala dependencias') {
            steps {
                script {
                    sh 'npm install'
                }
            }
        }

        stage('Executa testes') {
            steps {
                script {
                    sh 'npm run test'
                }
            }
        }

        stage('Criando container') {
            steps {
                script {
                    sh 'docker build -t trabalho .'
                }
            }
        }

        stage('Rodando container') {
            steps {
                script {
                    sh 'docker-compose up -d'
                }
            }
        }
    }

    post {
        success {
            echo 'Pipeline executado com sucesso!'
        }

        failure {
            echo 'Pipeline falhou. Verifique os logs para mais informações.'
        }
    }
}
