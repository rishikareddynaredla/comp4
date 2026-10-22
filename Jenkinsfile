pipeline {
    agent any
    
    tools {
        maven 'Maven3' // This matches the Name you set in Jenkins Tool Configuration
    }
    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }
        stage('Build and Package') {
            steps {
                bat 'mvn -B clean package'
            }
        }
    }

    post {
        success {
            archiveArtifacts artifacts: 'target/*.jar'
        }
    }
}
