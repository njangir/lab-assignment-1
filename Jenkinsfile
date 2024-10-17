pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/njangir/lab-assignment-1.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                script {
                    docker.build('mlops-python-app')
                }
            }
        }

        stage('Deploy') {
            steps {
                script {
                    docker.image('mlops-python-app').inside {
                        sh 'python temp.py'
                    }
                }
            }
        }
    }
}
