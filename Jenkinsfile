pipelin {
    agent any

    environment {
        GIT_REPO = 'https://github.com/Kanzcr/vulnadofront.git'
        GIT_CREDENTIALS = 'github-token-kanz'
    }

    stages {
        stage('Checkout') {
            steps {
                git url: "${GIT_REPO}", credentialsId: "${GIT_CREDENTIALS}"
            }
        }
        
        stage('Install Dependencies') {
            steps {
              bat 'npm install'
            }
        }
        
        stage('Build Frontend') {
            steps {
                bat 'npm run build'
            }
        }
        
        stage('Archive Build') {
            steps {
               arvhiveArtifacts artifacts: 'build/**'
            }
        }
    }
}