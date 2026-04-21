pipeline {
    agent any

    stages {

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t cloudpipeline-app .'
            }
        }

        stage('Run Container') {
            steps {
                sh '''
                docker rm -f cloudpipeline || true
                docker run -d -p 3000:3000 --name cloudpipeline cloudpipeline-app
                '''
            }
        }

        stage('Test') {
            steps {
                echo '🚀 CloudPipeline is Live!'
            }
        }
    }
}
