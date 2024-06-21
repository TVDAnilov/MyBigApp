pipeline {
    agent any

    stages {
        stage('Загрузка изменений из Git') {
            steps {
                git branch: 'master', url: 'https://github.com/TVDAnilov/Jenkins_tests.git'
            }
        }
        stage('TestFolder') {
            when { changeset "TestFolder/*"}
            steps {
                powershell 'Write-Host "TestFolder изменился!"'
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
                powershell ".\1.ps1"
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
                archiveArtifacts artifacts: '/**/*', followSymlinks: false
                powershell 'Write-Host "Сборка завершена!"'
                // Добавьте команды для отправки сообщения после сборки
            }
        }
        
    }
}