pipeline {
    agent any
    
    stages {
        stage('build api') {
            steps {
                echo "Ok"
            }
        }
        stage('build docker image') {
            steps {
                echo "Ok"
            }
        }
        stage('deploy docker image to repo') {
            steps {
                echo "Ok"
            }
        }
    }
    post {
        always {
            emailext body: 'A Test EMail', recipientProviders: [[$class: 'DevelopersRecipientProvider'], [$class: 'RequesterRecipientProvider']], subject: 'Test'
        }
    }
}
