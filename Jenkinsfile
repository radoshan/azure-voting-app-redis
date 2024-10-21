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
        stage('Start App') {
            steps {
                powershell 'docker compose up -d'
            }
        }
        stage('Run Tests') {
            steps {
                'pytest ./tests/test_sample.py'
            }
            post {
                success {
                    echo "Tests passed! :)"
                }
                failure {
                    echo "Tests failed! :("
                }
            }
        }
    }
    post {
        always {
            'docker compose down'
        }
    }
}