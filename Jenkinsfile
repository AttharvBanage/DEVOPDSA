pipeline {
    agent any

    stages {

        stage('Build Docker Image') {
            steps {
                bat 'docker build -t farmer-app .'
            }
        }

        stage('Run Container') {
            steps {
                bat 'docker rm -f farmer-jenkins || echo done'
                bat 'docker run -d -p 8096:80 --name farmer-jenkins farmer-app'
            }
        }
    }
}
