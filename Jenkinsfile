pipeline {
    agent any
    tools {
        maven 'maven-3.8.2'
    }
    environment {
        NEXUS_VERSION = "nexus3"
        NEXUS_PROTOCOL = "http"
        NEXUS_URL = "http://192.168.11.100:8081"
        NEXUS_REPOSITORY = "maven-public"
        NEXUS_CREDENTIAL_ID = "maven_nexus_credentials"
    }
    stages {
        /* stage ("Maven build") {
            steps {
                echo "======== maven build ========"
                sh "mvn -DskipTests=true clean package"
            }
        } */
        stage("Publish to Nexus") {
            steps {
                script {
                    nexusArtifactUploader artifacts: [
                        [
                            artifactId: 'blynk', 
                            classifier: '', 
                            file: 'target/blynk-0.41.17.jar', 
                            type: 'jar'
                        ]
                    ], 
                    credentialsId: 'maven_nexus_credentials', 
                    groupId: 'cc.blynk', 
                    nexusUrl: '192.168.11.100:8081', 
                    nexusVersion: 'nexus3', 
                    protocol: 'http', repository: 'blynk-server-release', version: '0.41.17'
                    
                    
                    /*
                    pom = readMavenPom file: "pom.xml"
                    echo "${pom}"
                    filesByGlob = findFiles(glob: "target/*.${pom.packaging}");
                    echo "${filesByGlob[0].name} ${filesByGlob[0].path} ${filesByGlob[0].directory} ${filesByGlob[0].length} ${filesByGlob[0].lastModified}"
                    artifactPath = filesByGlob[0].path;
                    artifactExists = fileExists artifactPath;
                    if(artifactExists) {
                        echo "*** File: ${artifactPath}, group: ${pom.groupId}, packaging: ${pom.packaging}, version ${pom.version}";
                        nexusArtifactUploader(
                            nexusVersion: NEXUS_VERSION,
                            protocol: NEXUS_PROTOCOL,
                            nexusUrl: NEXUS_URL,
                            groupId: pom.groupId,
                            version: pom.version,
                            repository: NEXUS_REPOSITORY,
                            credentialsId: NEXUS_CREDENTIAL_ID,
                            artifacts: [
                                [artifactId: pom.artifactId,
                                classifier: '',
                                file: artifactPath,
                                type: pom.packaging],
                                [artifactId: pom.artifactId,
                                classifier: '',
                                file: "pom.xml",
                                type: "pom"]
                            ]
                        );
                    } else {
                        error "*** File: ${artifactPath}, could not be found";
                    }
                }
                */
            } 
        }
    }
}
