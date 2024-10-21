pipeline {
    agent any

    stages {
        stage('Verify Branch') {
            steps {
                echo "$GIT_BRANCH"
            }
        }
        stage('Docker Build - bat') {
            steps {
                bat 'docker compose build'
            }
        }
        stage('Docker Build - powershell') {
            steps {
                powershell 'docker compose build'
            }
        }
        stage('Docker Build - sh') {
            steps {
                sh(script: 'docker compose')
            }
        }
    }
}