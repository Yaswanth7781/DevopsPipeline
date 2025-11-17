pipeline {
    agent any

    tools {
        jdk 'jdk17'
        maven 'maven'
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main',
                    credentialsId: 'github-token',
                    url: 'https://github.com/Yaswanth7781/DevopsPipeline.git'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean compile'
            }
        }

        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }

        stage('Package') {
            steps {
                sh 'mvn package'
            }
        }

        stage('Run Application') {
            steps {
                sh 'java -jar target/devops-app-1.0-SNAPSHOT.jar'
            }
        }
    }
}

