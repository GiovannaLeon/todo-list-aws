pipeline {
    agent any
    environment {
        // Variables para CD
        REGION = 'us-east-1'
        STACK_NAME = 'todo-list-aws-production'
    }
    stages {
        stage('Get Code') {
            steps {
                echo 'Obteniendo código de la rama master'
                git branch: 'master', url: 'https://github.com/GiovannaLeon/todo-list-aws.git'
            }
        }
        stage('Deploy to Production') {
            steps {
                echo 'Desplegando en producción'
                sh 'sam deploy --config-file samconfig.toml --config-env production'
            }
        }
}
  }
