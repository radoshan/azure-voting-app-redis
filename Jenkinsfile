pipeline {
    agent any

    stages {
        stage('Verify Branch') {
            steps {
                echo "$GIT_BRANCH"
            }
        }
        stage('Docker Build - powershell') {
            steps {
                powershell 'docker compose build'
            }
        }
    }
}