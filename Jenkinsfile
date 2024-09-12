pipeline {
    agent any
    stages {
        stage('Clone Repository') {
            steps {
               git branch: 'master', url: 'https://github.com/sarikabharath/my-java.git' 
            }
        }
        stage('Build') {
            steps {
                sh 'mvn compile'
            }
        }
        
        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }
        stage('Install') {
            steps {
                sh 'mvn clean install'
            }
        }
    }
    post {
        always {
            mail to: 'sarikaprakashb2gmail.com',
                 subject: 'Build Notification',
                 body: 'Please find the build results below:\n\nBuild Result: ${build success}'
        }
    }
}

