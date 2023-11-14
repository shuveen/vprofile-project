pipeline {
    agent any
    tools{
        maven "MAVEN3"
        jdk "OracleJDK11"
    }

    environment {
        SNAP_REPO = 'vprofile-snapshot'
        NEXUS_USER = 'admin'
        NEXUS_PASS = 'shuveen'
        RELEASE_REPO = 'vprofile-release'
        CENTRAL_REPO = 'vpro-maven-control'
        NEXUSIP = '172.31.32.20'
        NEXUSPORT = '8081'
        NEXUS_GRP_REPO = 'vpro-maven-group'
        NEXUS_LOGIN = 'nexuslogin'
    }

    stages {
        stage('Build'){
            steps{
                mvn clean install -s settings.xml 
                sh 'mvn -s settings.xml -DskipTests install'
            }
        }
    }
}