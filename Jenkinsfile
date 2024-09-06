pipeline {
    agent any

    triggers {
        pollSCM('H/5 * * * *') // Poll every 5 minutes for changes
    }

    stages {
        stage('Build') {
            steps {
                echo 'Building the code...'
            }
        }
        stage('Unit and Integration Tests') {
            steps {
                echo 'Running unit and integration tests...'
            }
        }
        stage('Code Analysis') {
            steps {
                echo 'Performing code analysis...'
            }
        }
        stage('Security Scan') {
            steps {
                echo 'Running security scan...'
            }
        }
        stage('Deploy to Staging') {
            steps {
                echo 'Deploying to staging server...'
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                echo 'Running integration tests on staging server...'
            }
        }
        stage('Deploy to Production') {
            steps {
                echo 'Deploying to production server...'
            }
        }
    }

    post {
        success {
            emailext (
                subject: "${JOB_NAME} - Build # ${BUILD_NUMBER} - Successful",
                body: "Build details: ${BUILD_URL}",
                to: "mboikhutso1@gmail.com"
            )
        }
        failure {
            emailext (
                subject: "${JOB_NAME} - Build # ${BUILD_NUMBER} - Failed",
                body: "Build details: ${BUILD_URL}",
                to: "mboikhutso1@gmail.com"
            )
        }
        unstable {
            emailext (
                subject: "${JOB_NAME} - Build # ${BUILD_NUMBER} - Unstable",
                body: "Build details: ${BUILD_URL}",
                to: "mboikhutso1@gmail.com"
            )
        }
    }
}
