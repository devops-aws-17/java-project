pipeline {
    agent any

    stages {
        stage('docker build') {
            steps {
                sh 'docket build -t javaspring:v1 .'
            }
        }
      stage('docker tag') {
            steps {
                sh 'docker tag javaspring:v1 prasadchandu/nag:javaspring'
            }
        }
      stage('docker login') {
            steps {
                sh 'docker login'
            }
        }
      stage('docker tag') {
            steps {
                sh 'docker push prasadchandu/nag:javaspring'
            }
        }
    }
}
