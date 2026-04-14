pipeline {
    agent any

    triggers {
        // Poll GitHub every 2 minutes for new commits
        pollSCM('H/2 * * * *')
    }

    environment {
        APP_NAME = 'MyApplication'
        BUILD_TOOL = 'maven'
        TEST_TOOL = 'junit'
        ANALYSIS_TOOL = 'sonarqube'
        SECURITY_TOOL = 'owasp-dependency-check'
        STAGING_SERVER = 'staging-server'
        PRODUCTION_SERVER = 'production-server'
    }

    stages {

        stage('1. Build') {
            steps {
                echo 'Stage 1: Build'
                echo 'Tool used: Maven / Gradle'
                echo 'Compiling source code and packaging the application...'

                // Example commands
                sh 'echo "Running Maven build..."'
                sh 'echo "mvn clean package"'
            }
        }

        stage('2. Unit and Integration Tests') {
            steps {
                echo 'Stage 2: Unit and Integration Tests'
                echo 'Tools used: JUnit, Selenium, TestNG, or Mockito'
                echo 'Running unit tests and integration tests to validate application behavior...'

                // Example commands
                sh 'echo "Running unit tests..."'
                sh 'echo "mvn test"'
                sh 'echo "Running integration tests..."'
                sh 'echo "mvn verify"'
            }
            post {
                always {
                    echo 'Test reports can be archived here.'
                }
            }
        }

        stage('3. Code Analysis') {
            steps {
                echo 'Stage 3: Code Analysis'
                echo 'Tool used: SonarQube / SonarCloud'
                echo 'Analysing source code quality, maintainability, and coding standard issues...'

                // Example commands
                sh 'echo "Running static code analysis..."'
                sh 'echo "mvn sonar:sonar"'
            }
        }

        stage('4. Security Scan') {
            steps {
                echo 'Stage 4: Security Scan'
                echo 'Tool used: OWASP Dependency-Check / Snyk'
                echo 'Scanning dependencies and code for known vulnerabilities...'

                // Example commands
                sh 'echo "Running security scan..."'
                sh 'echo "dependency-check.sh --scan ."'
            }
        }

        stage('5. Deploy to Staging') {
            steps {
                echo 'Stage 5: Deploy to Staging'
                echo 'Tool used: Docker / SSH / AWS EC2 / Kubernetes'
                echo 'Deploying the application to the staging environment...'

                // Example commands
                sh 'echo "Deploying build to staging server..."'
                sh 'echo "scp target/app.jar user@staging-server:/opt/app/"'
            }
        }

        stage('6. Integration Tests on Staging') {
            steps {
                echo 'Stage 6: Integration Tests on Staging'
                echo 'Tool used: Selenium / Postman / Newman / Cypress'
                echo 'Running integration and end-to-end tests on staging environment...'

                // Example commands
                sh 'echo "Running API/UI tests on staging..."'
                sh 'echo "newman run staging-tests.json"'
            }
        }

        stage('7. Deploy to Production') {
            steps {
                echo 'Stage 7: Deploy to Production'
                echo 'Tool used: Docker / SSH / AWS EC2 / Kubernetes'
                echo 'Deploying the validated application to the production environment...'

                // Example commands
                sh 'echo "Deploying application to production server..."'
                sh 'echo "scp target/app.jar user@production-server:/opt/app/"'
            }
        }
    }

    post {
        success {
            echo 'Pipeline completed successfully.'
        }
        failure {
            echo 'Pipeline failed. Please check the logs.'
        }
        always {
            echo 'Pipeline execution finished.'
        }
    }
}
