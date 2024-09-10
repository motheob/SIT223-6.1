pipeline {
    agent any
    
    stages {
        stage('Send Test Email') {
            steps {
                script {
                    emailext(
                        to: 'motheoboikhutsopublic@gmail.com',
                        subject: 'Test Email',
                        body: 'This is a test email sent from Jenkins.',
                        attachLog: true
                    )
                }
            }
        }
    }
}
