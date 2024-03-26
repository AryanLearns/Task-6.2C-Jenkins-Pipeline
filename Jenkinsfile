pipeline {
    agent any
    
    stages {
        stage('1. Build') {
            steps {
                // Dummy build step
                echo 'Building the code...'
            }
        }
        stage('2. Unit and Integration Tests') {
            steps {
                // Dummy unit and integration tests
                echo 'Running unit tests...'
                echo 'Unit tests passed.'
                
                echo 'Running integration tests...'
                echo 'Integration tests passed.'
            }
        }
        stage('3. Code Analysis') {
            steps {
                // Dummy code analysis
                echo 'Running code analysis...'
                echo 'Code analysis passed.'
            }
        }
        stage('4. Security Scan') {
            steps {
                // Dummy security scan
                echo 'Running security scan...'
                echo 'Security scan passed.'
            }
        }
        stage('5. Deploy to Staging') {
            steps {
                // Dummy deploy to staging
                echo 'Deploying to staging server...'
                echo 'Deployment to staging server successful.'
            }
        }
        stage('6. Integration Tests on Staging') {
            steps {
                // Dummy integration tests on staging
                echo 'Running integration tests on staging environment...'
                echo 'Integration tests on staging passed.'
            }
        }
        stage('7. Deploy to Production') {
            steps {
                // Dummy deploy to production
                echo 'Deploying to production server...'
                echo 'Deployment to production server successful.'
            }
        }
    }
    
    post {
        success {
            emailext subject: 'Pipeline Success',
                     body: 'The pipeline completed successfully.',
                     to: 'aryan7codefor1@gmail.com',
                     attachmentsPattern: '**/*'
        }
        failure {
            emailext subject: 'Pipeline Failure',
                     body: 'The pipeline has failed.',
                     to: 'aryan7codefor1@gmail.com',
                     attachmentsPattern: '**/*'
        }
    }
}
