pipeline {
    agent any

    stages {

        stage('Checkout SCM') {
            steps {
                git 'https://github.com/AttharvBanage/DEVOPDSA.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t group-project-app .'
            }
        }

        stage('Deploy Container') {
            steps {
                sh 'docker rm -f group-container || true'
                sh 'docker run -d -p 5020:80 --name group-container group-project-app'
            }
        }

        stage('Post Actions') {
            steps {
                echo 'Deployment Successful'
            }
        }
    }
}
