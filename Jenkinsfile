pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Building the code...'
                echo 'Tool: Maven'
                // Example: sh 'mvn clean install'
            }
        }
        stage('Unit and Integration Tests') {
            steps {
                echo 'Running unit and integration tests...'
                echo 'Tool: JUnit, TestNG'
                // Example: sh 'mvn test'
            }
            post {
                success {
                    echo 'Unit and integration tests passed.'
                    emailext attachLog: true, 
                             body: 'Unit and integration tests passed successfully.',
                             subject: 'Test Success',
                             to: 'rajgariwala40302@gmail.com'
                }
                failure {
                    echo 'Unit and integration tests failed.'
                    emailext attachLog: true, 
                             body: 'Unit and integration tests failed. Please check the logs for details.',
                             subject: 'Test Failure',
                             to: 'rajgariwala40302@gmail.com'
                }
            }
        }
        stage('Code Analysis') {
            steps {
                echo 'Performing code analysis...'
                echo 'Tool: SonarQube'
                // Example: sh 'sonar-scanner'
            }
        }
        stage('Security Scan') {
            steps {
                echo 'Performing security scan...'
                echo 'Tool: OWASP ZAP'
                // Example: sh 'zap-cli --quick-scan --spider <target-url>'
            }
            post {
                success {
                    echo 'Security scan passed.'
                    emailext attachLog: true, 
                             body: 'Security scan passed successfully.',
                             subject: 'Security Scan Success',
                             to: 'rajgariwala40302@gmail.com'
                }
                failure {
                    echo 'Security scan failed.'
                    emailext attachLog: true, 
                             body: 'Security scan failed. Please check the logs for details.',
                             subject: 'Security Scan Failure',
                             to: 'rajgariwala40302@gmail.com'
                }
            }
        }
        stage('Deploy to Staging') {
            steps {
                echo 'Deploying to staging environment...'
                echo 'Staging server: AWS EC2'
                // Example: sh 'aws ecs deploy ...'
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                echo 'Running integration tests on staging environment...'
                // Run integration tests on staging environment
                // Example: sh 'robot <test-file>.robot'
            }
        }
        stage('Deploy to Production') {
            steps {
                echo 'Deploying to production environment...'
                echo 'Production server: AWS EC2'
                // Example: sh 'aws ecs deploy ...'
                echo 'This message is set to check whether the build triggers dynamically or not'
            }
        }
    }
}
