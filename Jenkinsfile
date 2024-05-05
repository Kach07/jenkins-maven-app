pipeline {
    agent any
 
    stages {
        stage('Clone') {
            steps {
               git 'https://github.com/Kach07/jenkins-maven-app.git'
            }
        }
        stage('Build Docker Image') {
            steps {
                script {
                    // Build Docker image
                    docker.build('maven-app:latest', '-f .')
                }
            }
        }
        // stage('Push Docker Image') {
        //     steps {
        //         script {
        //             // Push Docker image to registry
        //             docker.withRegistry('https://registry.example.com', 'credentials_id') {
        //                 docker.image('your_image_name:your_image_tag').push('latest')
        //             }
        //         }
        //     }
        // }
        stage('Deploy Docker Container') {
            steps {
                script {
                    // Deploy Docker container using Docker Compose
                    sh 'docker-compose -f docker-compose.yml up -d'
                }
            }
        }
    }
}