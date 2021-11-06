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
                sh "cp /var/lib/jenkins/workspace/Blynk-server/server/launcher/target/server-*.jar /home/yaroslav/Docker"
                sh "cd /home/yaroslav/Docker"
                sh "docker build -f /home/yaroslav/Docker/Dockerfile -t blynk-server ."
                
            }
        }
    } 
    

}
