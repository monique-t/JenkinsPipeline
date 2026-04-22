pipeline {
    
    agent any 
    
    environment {
        //The path of the code directory being fetched.
        DIRECTORY_PATH = "/var/lib/jenkins/workspace/GitHub_Pipeline"
        // The name of the staging environment.
        STAGING_ENVIRONMENT = "AWS EC2 STAGE"
        // The name of the production environment.
        PRODUCTION_ENVIRONMENT = "AWS EC2 PROD"
    }

    stages {
// Stage 1: Build – Build the code using a build automation tool to compile and package
// your code. You need to specify at least one build automation tool, e.g., Maven.
        stage('Build') {
            steps {
                echo "fetch the source code from the directory path specified by the environment variable: ${DIRECTORY_PATH}"
                echo "Call mvn - compile the code and generate any necessary artefacts - using Maven"
            }
        }
// Stage 2: Unit and Integration Tests – Run unit tests to ensure the code functions as
// expected and run integration tests to ensure the different components of the
// application work together as expected. 
// You need to specify test automation tools for this stage.
        stage('Unit and Integration Tests') {
            steps {
                echo "Run unit tests - using JUnit"
                echo "Run integration tests - using Selenium"
                // sh 'mvn test'
            }
        }
// Stage 3: Code Analysis – Integrate a code analysis tool to analyse the code and ensure
// it meets industry standards. Research and select a tool to analyse your code using Jenkins
        stage('Code Analysis') {
            steps {
                echo "Check the quality of the code - using SonarQube (SAST test)"
            }
        }

// Stage 4: Security Scan – Perform a security scan on the code using a tool to identify
// any vulnerabilities. Research and select a tool to scan your code.
        stage('Security Scan') {
            steps {
                echo "Perform security scan for vulnerabilities - using Zed Attack Proxy (ZAP) (DAST test)"
            }
        }
// Stage 5: Deploy to Staging – Deploy the application to a staging server (e.g., AWS EC2 instance).
        stage('Deploy to Staging') {
            steps {
                echo "Deploy the application to a staging environment: ${STAGING_ENVIRONMENT}"
            }
        }
// Stage 6: Integration Tests on Staging – Run integration tests on the staging
// environment to ensure the application functions as expected in a production-like environment.       
        stage('Integration Tests on Staging') {
            steps {
                echo 'Run integration tests on staging - using Selenium'
                echo "manual approval pending (simulated)"
                sleep 10
            }
        }
// Stage 7: Deploy to Production – Deploy the application to a production server (e.g. AWS EC2 instance).
        stage('Deploy to Production') {
            steps {
                echo "deploy code to the production environment: ${PRODUCTION_ENVIRONMENT}"
            }
        }
    }
}
