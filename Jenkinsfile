pipeline {
    agent { label 'slave1' } /****/****/***
    tools
    {
        jdk 'java17'
        maven 'maven3'
    }
    stages {
        stage('clean workspace') {
            steps {
                cleanWs()
            }
        }
        stage('git checkout') {
            steps {
                checkout scmGit(branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[credentialsId: 'github', url: 'https://github.com/devops-aws-17/java-project.git']])
            }
        }
        
        stage('build application') {
            steps {
                sh 'mvn clean package'
            }
        }
      stage('maven test') {
            steps {
                sh 'mvn test'
            }
        }
    }
}
