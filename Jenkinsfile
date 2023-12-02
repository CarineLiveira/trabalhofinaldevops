pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('instalando dependências') {
            steps {
                script {
                    sh 'npm install'
                }
            }
        }

        stage('executando testes presentes no projeto') {
            steps {
                script {
                    sh 'npm run test'
                }
            }
        }

        stage('criando container docker') {
            steps {
                script {
                    sh 'docker build -t trabalho-final-devops .'
                }
            }
        }

        stage('subindo coosjfvnjodfnojdfnvo') {
            steps {
                script {
                    sh 'docker-compose up -d'
                }
            }
        }
    }

    post {
        success {
            echo 'pipipopo'
        }

        failure {
            echo 'botafogo'
        }
    }
}
