pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo "Fetching the source code from GitHub"
                echo "Compiling the code and generating artifacts"
                echo "updated"
            }
        }
        stage('Unit and Integration Tests') {
            steps {
                echo "Running unit tests started and completed"
                echo "Running integration tests started and completed"
            }
            post {
                success {
                    mail to: 'aryansingh57602@gmail.com',
                        subject: 'Unit and Integration Tests Success',
                        body: 'The unit and integration tests have succeeded. Find attached logs for more information.'
                }
                failure {
                    mail to: 'aryansingh57602@gmail.com',
                        subject: 'Unit and Integration Tests Failed',
                        body: 'The unit and integration tests have failed. Find attached logs for more information.'
                }
            }
        }
        stage('Code Analysis') {
            steps {
                echo "Running Code Analysis started and completed"
            }
        }
        stage('Security Scan') {
            steps {
                echo "Running Security Scan started and completed"
            }
            post {
                success {
                    mail to: 'aryansingh57602@gmail.com',
                        subject: 'Security Scan Success',
                        body: 'The Security Scan has succeeded. Find attached logs for more information.'
                }
                failure {
                    mail to: 'aryansingh57602@gmail.com',
                        subject: 'Security Scan Failed',
                        body: 'The Security Scan has failed. Find attached logs for more information.'
                }
            }
        }
        stage('Deploy to Staging') {
            steps {
                echo "Running Deploy to Staging started and completed"
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                echo "Running Integration Tests on Staging started and completed"
            }
            post {
                success {
                    mail to: 'aryansingh57602@gmail.com',
                        subject: 'Integration Tests on Staging Success',
                        body: 'The Integration Tests on Staging have succeeded. Find attached logs for more information.'
                }
                failure {
                    mail to: 'aryansingh57602@gmail.com',
                        subject: 'Integration Tests on Staging Failed',
                        body: 'The Integration Tests on Staging have failed. Find attached logs for more information.'
                }
            }
        }
        stage('Deploy to Production') {
            steps {
                echo "Running Integration Tests on Staging started and completed"
            }
        }
    }
}
