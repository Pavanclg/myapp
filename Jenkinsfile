pipeline {
    agent any

    stages {

        stage('Clone') {
            steps {
                git 'https://github.com/pavanclg/myapp.git'
            }
        }

        stage('Build Maven') {
            steps {
                sh 'mvn clean package'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t java-maven-app .'
            }
        }

        stage('Run Docker Container') {
            steps {
                sh 'docker run --rm java-maven-app'
            }
        }
    }
}
