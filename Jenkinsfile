pipeline {
    agent any
    stages {
        stage('build sample project') {
            steps {
                git 'https://github.com/ashakirin/spring-rest-foo.git'
                sh 'mvn --version'
                sh 'mvn clean install'
                sh 'mvn jib:build'
            }
        }
    }
}