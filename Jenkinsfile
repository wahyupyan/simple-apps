pipeline {
    agent {
        node {
            label 'devops1-wahyu'
        }
    }    

    stages {
        stage('Build Apps') {
            steps {
                sh '''
                cd app
                npm install
                '''
            }
        }
        stage('Testing Apps') {
            steps {
                sh '''
                cd app
                npm test
                npm run test:coverage
                '''
            }
        }
        stage('Scanning Apps') {
            steps {
                sh '''
                cd app
                sonar-scanner  -Dsonar.projectKey=Simple-Apps   -Dsonar.sources=.   -Dsonar.host.url=http://172.23.10.12:9000   -Dsonar.login=sqp_9328fa93f1c112fef84af1db52f17a1aefe69b14
                '''
            }
        }
        stage('Scanning Code ') {
            steps {
                echo 'Scanning Code'
            }
        }
        stage('Dockerized') {
            steps {
                sh '''
                docker compose build
                '''
            }
        }
        stage('Push Image') {
            steps {
                sh '''
                docker compose push
                '''
            }
        }
        stage('Deploy to Docker') {
            steps {
                sh '''
                docker compose up -d
                '''
            }
        }
    }
}