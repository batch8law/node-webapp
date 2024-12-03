pipeline {
    agent {  
        label 'linux-node'  
    }  
    stages {
        stage('Checkout') {  
            steps {  
                git credentialsId: 'batch8law', url: 'https://github.com/batch8law/node-webapp.git', branch: 'main'
            }  
        }  
        stage('Build Docker Image') {
            steps {  
                script {  
                    docker.build('node-webapp:latest')
                }
            }  
        }  
        stage('Run Docker Container') {
            steps {  
                script {  
                    docker.image('node-webapp:latest').run('-d -p 3000:3000')
                }  
            }  
        }
    }  
}
