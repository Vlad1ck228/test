pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps {
                script {
                    docker.build('my-website1:latest')
                }
            }
        }
        stage('Test') {
            steps {
            }
        }
        stage('Deploy') {
            steps {
                script {
                    docker.withRegistry('https://hub.docker.com/u/vladhl', 'vladhl') {
                        docker.image('my-website:latest').push('latest')
                    }
                }
            }
        }
    }
    
    post {
        always {
        }
    }
}
