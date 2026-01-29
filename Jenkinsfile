pipeline{
    agent any

    stages{
        stage('checkout'){
            steps{
                checkout scm
            }
        }
         stage('Build Docker Image'){
            steps{
                sh 'docker build -t jenkinsapp:latest .'
            }
        }
        stage('Run Container'){
            steps{
                sh '''
                docker rm -f demo || true
                docker run -d -p 5000:5000 --name demo jenkinsapp:latest
                '''
            }
        }
    }
}
