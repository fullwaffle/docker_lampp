pipeline {
    agent any

    stages {
        stage('clone') {
            steps {
                git 'https://github.com/fullwaffle/docker_lemp'
            }
        }

        stage('build') {
            steps {
                sh 'docker-compose build'
            }
        }

        stage('run and test') {
            steps {
                sh '''
                docker-compose up -d
                curl localhost:8081
                '''
            }
        }
    }
}