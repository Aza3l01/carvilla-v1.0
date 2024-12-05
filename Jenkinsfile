pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh 'docker build -t my-website .'
            }
        }
        stage('Deploy') {
            steps {
                sh '''
                docker stop brave_goldstine || true
                docker rm brave_goldstine || true
                docker run -d --name brave_goldstine -p 8080:80 my-website
                '''
            }
        }
    }
}
