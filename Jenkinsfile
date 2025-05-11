pipeline {
    agent any
    stages {
        stage('Build') {
            steps { echo 'Maven: mvn clean package' }
        }
        stage('Unit & Integration Tests') {
            steps { echo 'JUnit via Surefire, Postman/Newman for API ITs' }
        }
        stage('Code Analysis') {
            steps { echo 'SonarScanner or PMD/SpotBugs' }
        }
        stage('Security Scan') {
            steps { echo 'OWASP Dependency-Check or Snyk CLI' }
        }
        stage('Deploy to Staging') {
            steps { echo 'ansible-playbook deploy-staging.yml' }
        }
        stage('Integration Tests on Staging') {
            steps { echo 'Cypress e2e against staging URL' }
        }
        stage('Deploy to Production') {
            steps { echo 'ansible-playbook deploy-dev.yml' }
        }
    }
}
