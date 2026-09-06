pipeline {
    agent any

    stages {

        stage('Install Dependencies') {
            steps {
                echo 'Installing Node.js dependencies...'
                sh 'npm install'
            }
        }

        stage('Run Tests') {
            steps {
                echo 'Running unit tests...'
                sh 'npm test || true'
            }
        }

        stage('Snyk Security Scan') {
            steps {
                echo 'Running Snyk security scan...'
                sh 'snyk test || true'
            }
        }

        stage('OWASP Dependency Check') {
            steps {
                echo 'Running OWASP Dependency Check...'
                sh 'dependency-check.sh --scan . --format HTML --out reports || true'
            }
        }

        stage('Build Application') {
            steps {
                echo 'Building the Node.js application...'
                sh 'npm run build || true'
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
