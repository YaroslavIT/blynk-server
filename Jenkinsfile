pipeline {
    agent any
    tools {
        maven 'maven-3.8.2'
    }
    stages {
        stage ("Maven build") {
            steps {
                echo "======== maven build ========"
                sh "mvn dependency::tree"
                sh "mvn clean package -X"
            }
        }
    }
}
