pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }
        stage('Restore .Net packages') {
            steps {
                bat 'dotnet restore'
            }
        }
        stage('Build .Net project') {
            steps {
                bat 'dotnet build --no-restore'
            }
        }
        stage('run and test') {
            steps {
                bat 'dotnet test --no-build --verbosity normal'
            }
        }
    }
}