pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
               sh 'mvn install'
            }
        }
        stage('Build the docker image') {
            steps {
               sh 'docker build -t samikban/spring-petclinic-0601:v1.3 . && docker images'
               sh 'docker images'
            }
        }
    }
}
