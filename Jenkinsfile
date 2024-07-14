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
                echo 'Testing Apps'
            }
        }
        stage('Scanning Apps') {
            steps {
                echo 'Scanning Apps'
            }
        }
        stage('Scanning Code ') {
            steps {
                echo 'Scanning Code'
            }
        }
        stage('Dockerized') {
            steps {
                echo 'Dockerized'
            }
        }
        stage('Push Image') {
            steps {
                echo 'Push Image'
            }
        }
        stage('Deploy to Docker') {
            steps {
                echo 'Deploy to Docker'
            }
        }
    }
}