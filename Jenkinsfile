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
                sh 'g++ main/hello.cpp -o output' 
                sh 'g++ working.cpp -o working'
            }
        }

        stage('Test') {
            steps {
                sh './output'
                sh './working'
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