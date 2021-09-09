pipeline {
    agent any
    environment {
        registryCredential = 'dockerhub'
    }
    stages {
        stage('Build') {
            steps {
                    //sh 'docker build -t mohsinm/backend .'
                    sh 'docker build -t frontend .'
                    sh 'docker tag frontend mohsinm/frontend:third'
            }
        }
        // stage('Test') {
        //     steps {
        //         sh 'docker container rm -f node || true'
        //         sh 'docker container run -p 8081:8080 --name backend node -d mohsinm/backend'
        //         sh 'docker container run -p 8082:8080 --name frontend -d mohsinm/frontend'
        //         sh 'curl -I http://localhost:8082'
        //     }
        // }
        stage('Publish') {
            steps{
                script {
                    docker.withRegistry( '', registryCredential ) {
                        //sh 'docker push mohsinm/backend:latest'
                        sh 'docker push mohsinm/frontend:third'
                    }
                }
            }
        }
    }
}
