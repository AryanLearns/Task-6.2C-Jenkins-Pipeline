pipeline {
    agent any
    
    stages {
        stage('1. Build') {
            steps {
                // Use Maven to build the code
                sh 'mvn clean package'
            }
        }
        stage('2. Unit and Integration Tests') {
            steps {
                // Run unit tests
                sh 'mvn test'
                
                // Run integration tests
                // Replace 'run_integration_tests.sh' with your actual script to run integration tests
                sh './run_integration_tests.sh'
            }
        }
        stage('3. Code Analysis') {
            steps {
                // Run code analysis using SonarQube scanner
                withSonarQubeEnv('SonarQube') {
                    sh 'mvn sonar:sonar'
                }
            }
        }
        stage('4. Security Scan') {
            steps {
                // Run security scan using OWASP ZAP
                // Replace 'run_security_scan.sh' with your actual script to run security scan
                sh './run_security_scan.sh'
            }
        }
        stage('5. Deploy to Staging') {
            steps {
                // Deploy to staging server using AWS CLI
                // Replace 'deploy_to_staging.sh' with your actual script to deploy to staging
                sh './deploy_to_staging.sh'
            }
        }
        stage('6. Integration Tests on Staging') {
            steps {
                // Run integration tests on staging environment
                // Replace 'run_integration_tests_staging.sh' with your actual script to run integration tests on staging
                sh './run_integration_tests_staging.sh'
            }
        }
        stage('7. Deploy to Production') {
            steps {
                // Deploy to production server using AWS CLI
                // Replace 'deploy_to_production.sh' with your actual script to deploy to production
                sh './deploy_to_production.sh'
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
