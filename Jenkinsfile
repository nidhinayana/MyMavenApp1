pipeline {
    agent any  // Use any available agent

    tools {
        maven 'Maven'  // Make sure 'Maven' is configured in Jenkins tools
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/nidhinayana/MyMavenApp1.git'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean package'  // Build the project
            }
        }

        stage('Test') {
            steps {
                sh 'mvn test'  // Optional if tests are already run during 'package'
            }
        }

        stage('Run Application') {
            steps {
                sh 'java -jar target/MyMavenApp1-1.0-SNAPSHOT.jar'  // Fixed path and removed extra quote
            }
        }
    }

    post {
        success {
            echo 'Build and deployment successful!'
        }
        failure {
            echo 'Build failed!'
        }
    }
}

