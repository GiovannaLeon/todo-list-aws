pipeline {
    agent any
    environment {
        // Variables para CI
        REGION = 'us-east-1'
        STACK_NAME = 'todo-list-aws-staging'
    }
    stages {
        stage('Get Code') {
            steps {
                echo 'Obteniendo código de la rama develop'
                git branch: 'develop', url: 'https://github.com/GiovannaLeon/todo-list-aws.git'
            }
        }
        stage('Static Analysis') {
            steps {
                echo 'Analizando estáticamente el código'
                sh 'flake8 src/'
                sh 'bandit -r src/'
            }
        }
        // Resto de etapas CI (tests, construcción, etc.)
    }
}
