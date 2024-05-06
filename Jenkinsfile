pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                script {
                    checkout scmGit(branches: [[name: '*/main']], 
                                    extensions: [[$class: 'SparseCheckoutPaths', sparseCheckoutPaths: [[path: '3/6']]]],
                                    userRemoteConfigs: [[url: 'https://github.com/TVDAnilov/MyBigApp.git']])
                }
            }
        }
        stage('Приветствие') {
            steps {
                powershell 'Write-Host "Привет, мир!"'
            }
        }

        stage('Сборка') {
            steps {
                powershell 'Write-Host "Выполняется сборка..."'
                // Добавьте команды для сборки вашего проекта
            }
        }

        stage('Тесты') {
            steps {
                powershell 'Write-Host "Выполняются тесты..."'
                // Добавьте команды для запуска тестов
            }
        }

        stage('Сообщение после сборки') {
            steps {
                powershell 'Write-Host "Сборка завершена!"'
                // Добавьте команды для отправки сообщения после сборки
            }
        }
    }
}