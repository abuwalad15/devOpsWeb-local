pipeline {
    agent any
    tools{
        maven 'maven-3.9.9'
    }

    stages {
        stage('Build') {
            steps {
                sh 'mvn clean install'
            }
        }

        stage('Deploy to tomcat server') {
            steps {
                    deploy adapters: [tomcat9(credentialsId: 'a52389b4-4d66-4db2-a23d-08159d4ecf60', path: '', url: 'http://localhost:8080/')], contextPath: 'devOpsWeb-local', war: 'target/*.war'                
            }

        }
    }
}
