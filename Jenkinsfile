pipeline {
    agent any

    stages {

        stage('1. Build') {
            steps {
                echo 'Building the application using a tool like Maven or Gradle...'
            }
        }

        stage('2. Unit and Integration Tests') {
            steps {
                echo 'Running unit and integration tests using tools like JUnit or Selenium...'
            }
        }

        stage('3. Code Analysis') {
            steps {
                echo 'Performing static code analysis using tools like SonarQube...'
            }
        }

        stage('4. Security Scan') {
            steps {
                echo 'Running security scan using tools like OWASP Dependency Check or Snyk...'
            }
        }

        stage('5. Deploy to Staging') {
            steps {
                echo 'Deploying application to staging server (e.g., AWS EC2)...'
            }
        }

        stage('6. Integration Tests on Staging') {
            steps {
                echo 'Running integration tests on staging environment...'
            }
        }

        stage('7. Deploy to Production') {
            steps {
                echo 'Deploying application to production server...'
            }
        }
    }
}
