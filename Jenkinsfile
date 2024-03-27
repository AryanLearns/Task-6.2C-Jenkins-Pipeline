pipeline {
  // Allow jobs to run on any agent (e.g., virtual machines)
  agent any

  // Define environment variables
  environment {
    TESTING_ENVIRONMENT = "junit"
    PRODUCTION_ENVIRONMENT = "Aryan Singh" 
  }

  // Define stages in the pipeline
  stages {
    // Build stage
    stage('Build') {
      steps {
        echo "Fetching source code from ${env.DIRECTORY_PATH}"
        echo "Building the code using Maven" // Corrected grammar
      }
    }

    // Unit and integration tests stage
    stage('Unit and Integration Tests') { // Improved capitalization
      steps {
        echo "Running unit and integration tests using JUnit"
      }
      post {
        success {
          emailext subject: 'Success: Testing Stage',
                   body: 'Tests ran successfully!', // Added exclamation mark
                   to: "aryansingh57602@gmail.com", // Updated email recipient
                   attachLog: true
        }
        failure {
          emailext subject: 'Failure: Testing Stage',
                   body: 'Failed to run tests.', // Added period
                   to: "aryansingh57602@gmail.com", // Updated email recipient
                   attachLog: true
        }
      }
    }

    // Code analysis stage
    stage('Code Analysis') {
      steps {
        echo "Checking code quality using SonarQube"
      }
    }

    // Security scan stage
    stage('Security Scan') {
      steps {
        echo "Performing security scan using Snyk"
      }
      post {
        success {
          emailext subject: 'Success: Security Scan',
                   body: 'Security scan successful!', // Added exclamation mark
                   to: "aryansingh57602@gmail.com", // Updated email recipient
                   attachLog: true
        }
        failure {
          emailext subject: 'Failure: Security Scan',
                   body: 'Security scan failed.', // Added period
                   to: "aryansingh57602@gmail.com", // Updated email recipient
                   attachLog: true
        }
      }
    }

    // Deploy to staging stage
    stage('Deploy to Staging') {
      steps {
        echo "Deploying to staging server (AWS EC2)"
      }
    }

    // Integration tests on staging stage
    stage('Integration Tests on Staging') { // Improved capitalization
      steps {
        echo "Running integration tests using Apache Camel tool"
        echo "Updating code (Note: This action might not be intended here)" // Added clarification
      }
    }

    // Deploy to production stage
    stage('Deploy to Production') {
      steps {
        echo "Deploying application to production server (AWS EC2 instance)"
    }
  }
}
