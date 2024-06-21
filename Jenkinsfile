pipeline {
    agent any
    stages {
        stage('Copy Archive') {
            steps {
                script {
                    step ([$class: 'Copy_Artifact',
                        projectName: 'MyBiiigApp',
                        filter: "*",
                        target: 'Infra']);
                }
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