pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                // Checkout code from GitHub repository
                git 'https://github.com/Ahsan-Khan07/jenkins-elk.git'
            }
        }
        stage('Start Elasticsearch Container') {
            steps {
                // Start Elasticsearch container using Docker Compose
                script {
                    dockerComposeFile = 'docker-compose.yml"'
                    dockerComposeYaml = readFile(dockerComposeFile)
                    sh "docker-compose -f $dockerComposeFile up -d"
                }
            }
        }
    }
    // post {
    //     always {
    //         // Clean up: Stop and remove container
    //         script {
    //             sh 'docker-compose -f docker-compose.yml down'
    //         }
    //     }
    // }
}

