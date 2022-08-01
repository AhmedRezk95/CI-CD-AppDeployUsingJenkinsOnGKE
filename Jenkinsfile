pipeline {
    agent any
    stages {
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