pipeline {
    agent any

    tools {
        maven 'demo-maven'
    }

    stages {

        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }

        stage('Trivy Scan') {
            steps {
                sh 'trivy fs .'
            }
        }

        stage('Test') {
            steps {
                sh 'java -cp target/maven-trivy-lab-1.0.jar App'
            }
        }
    }
}
