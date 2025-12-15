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
                archiveArtifacts artifacts: 'build/**'
            }
        }

       stage('Deploy to dev') {
         when {
        expression { false }   // selalu skip
    }
    steps {
        bat 'scp -r build/* kanz@10.100.0.36:/Users/kanz/dev-server/html'
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
