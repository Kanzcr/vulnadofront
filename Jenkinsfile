pipeline {
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
<<<<<<< HEAD
                archiveArtifacts artifacts: 'build/**'
            }
        }

        stage('Deploy to dev') {
            steps {
                // Deployment command
                bat 'scp -r build/* user@dev-server:/var/www/html'
            }
        }
    }

    post {
        success {
            echo 'Build Sukses!'
        }
        failure {
            echo 'Build Gagal!'
        }
    }
}
>>>>>>> 67ee1ce53c3d83d7f4f4947d022db25fe66f05b7
