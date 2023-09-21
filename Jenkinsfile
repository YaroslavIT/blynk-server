pipeline {
    agent docker
    tools {
        maven 'maven-3.9.4'
    }
    stages {
        stage ("Maven build") {
            steps {
                echo "======== MAVEN BUILD ========"
                /*sh "mvn -DskipTests=true clean package" */
                sh "mvn clean install -Dmaven.test.skip=true"
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
