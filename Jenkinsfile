pipeline {
    agent any

    stages {
        stage('Clonar o repositorio') {
            steps {
               git branch: 'main', url: 'https://github.com/Patriciadias2014/exercicio-modulo-14.git'
            }
        }
        stage('Instalar dependencias') {
            steps {
               sh 'npm install'
            }   
        }
         stage('Subir servidor') {
            steps {
               sh 'npm start'
            }   
        }
        stage('Executar testes') {
            steps {
               sh 'NO_COLOR=1 npm run cy:run'
            }
        }
        stage('Criar relatorio mocha') {    
            steps {
               sh 'npm run cy:report'
            }
        }
    }
}