pipeline {
    agent any
    stages {
        stage('build sample project') {
            steps {
                withCredentials([usernamePassword(credentialsId: 'dockerhub', usernameVariable: 'DOCKERHUB_USERNAME', passwordVariable: 'DOCKERHUB_PASSWORD')]) {
                    git 'https://github.com/ashakirin/spring-rest-foo.git'
                    sh 'mvn --version'
                    sh 'mvn clean install'
                    sh 'mvn jib:build -Djib.to.auth.username=${DOCKERHUB_USERNAME} -Djib.to.auth.password=${DOCKERHUB_PASSWORD}'
                }
            }
        }
    }
}