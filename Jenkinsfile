pipeline {
    agent any

    tools {
        maven 'Maven'  // Replace with your configured Maven tool name in Jenkins   
    }
    stages {
        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }

        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }

        stage('Run Application') {
            steps {
                // Updated JAR name based on Maven output
                sh 'java -jar target/my-app-1.0-SNAPSHOT.jar'
            }
        }
    }

    post {
        failure {
            echo 'Build failed!'
        }
    }
}
