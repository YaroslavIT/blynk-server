pipeline {
    agent any
    tools {
        maven 'maven-3.8.2'
    }
    stages {
        stage ("Maven build") {
            steps {
                echo "======== MAVEN BUILD ========"
                /*sh "mvn -DskipTests=true clean package" */
                // sh "mvn clean package -DskipTests"
            }
        }
        stage ("Docker build") {
            steps {
                echo "======== DOCKER BUILD ========"
                sh "docker build -f ./server/Docker/Dockerfile -t blynk-server ."
                
            }
        }
    } 
    

}
