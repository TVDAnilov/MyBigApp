pipeline {
    agent any
    //parameters {
    //    string(name: 'GIT_FILTER', defaultValue: 'MyBigApp/3/6/2/*', description: 'Git LFS filters to apply during git clone (--filter)')
    //}
    stages {
        stage('Checkout') {
            steps {
                script {
                    checkout([$class: 'GitSCM', 
                            branches: [[name: 'main']], 
                            userRemoteConfigs: [[url: 'https://github.com/TVDAnilov/MyBigApp.git']], 
                            extensions: [[$class: 'PathRestriction', excludedRegions: '', includedRegions: 'MyBigApp/3/6/2']]])
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