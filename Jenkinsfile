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
        stage('Run the docker image') {
            steps {
               sh 'docker run -d -p 80:8080 --name=spring-app-container samikban/spring-petclinic-0601:v1.3'
               sh 'sleep 20'
               sh 'docker ps'
               sh 'docker stop spring-app-container'
               sh 'docker images'
            }
        }
    }
}
