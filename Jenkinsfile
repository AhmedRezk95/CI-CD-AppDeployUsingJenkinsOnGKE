pipeline {
    agent any
    stages {
        input {
                message "Should we create it?"
                ok "yes"
                submitter "admin"
            }
        stage('create namespace') {
            steps {
                sh """
                    kubectl create namespace app
                """
            }
        }

        stage('install the application') {
            steps {
                sh """
                    kubectl apply -Rf ./k8-yamls
                """
            }
        }
    }
    
}