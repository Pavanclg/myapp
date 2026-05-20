pipeline {

    agent { label 'java-agent' }

    triggers {
        cron('H/2 * * * *')
    }

    stages {

        stage('Clone') {
            steps {
                git branch: 'main',
                url: 'https://github.com/Pavanclg/myapp.git'
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
