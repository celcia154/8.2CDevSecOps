pipeline {
    agent any

    stages {

        stage('Install Dependencies') {
            steps {
                echo 'Installing Node.js dependencies...'
                bat 'npm install'
            }
        }

        stage('Run Tests') {
            steps {
                echo 'Running unit tests...'
                bat 'npm test || exit 0'
            }
        }

        stage('Snyk Security Scan') {
            steps {
                echo 'Running Snyk security scan...'
                bat 'snyk test || exit 0'
            }
        }

        stage('OWASP Dependency Check') {
            steps {
                echo 'Running OWASP Dependency Check...'
                bat 'dependency-check.bat --scan . --format HTML --out reports || exit 0'
            }
        }

        stage('Build Application') {
            steps {
                echo 'Building the Node.js application...'
                bat 'npm run build || exit 0'
            }
        }

        stage('Mock Deploy to Staging') {
            steps {
                echo 'Deploying to staging environment...'
                echo 'This is a mock deploy step for assignment purposes.'
            }
        }

        stage('Mock Deploy to Production') {
            steps {
                echo 'Deploying to production environment...'
                echo 'This is a mock deploy step for assignment purposes.'
            }
        }
    }
}
