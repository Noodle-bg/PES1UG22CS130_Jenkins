pipeline {
    agent any 
    stages {
        stage('Clone repository') {
            steps {
                checkout([$class: 'GitSCM', 
                branches: [[name: '*/main']], 
                userRemoteConfigs: [[url: 'https://github.com/Noodle-bg/PES1UG22CS130_Jenkins.git']]])
            }
        }

        stage('Build') {
            steps {
                sh 'g++ main/main.cpp -o output' 
            }
        }

        stage('Test') {
            steps {
                sh './output'
            }
        }

        stage('Deploy') {
            steps {
                echo 'deploy' 
            }
        }
    }

    post {
        failure {
            echo 'Pipeline failed'
        }
    }
}