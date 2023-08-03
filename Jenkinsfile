pipeline {
    agent any

    stages {
        stage('Git Checkout') {
            steps {
                script {
                    git branch: 'main', url: 'https://github.com/mallick700/demo-counter-app.git'
                }
            }
        }

        stage('UNIT testing') {
            steps {
                script {
                    sh 'mvn clean package'
                    sh 'mvn test'
                }
            }
        }

        stage('Integration testing') {
            steps {
                script {
                    sh 'mvn verify -DskipTests'
                }
            }
        }

        stage('Maven build') {
            steps {
                script {
                    sh 'mvn clean install'
                }
            }
        }
    }
}
