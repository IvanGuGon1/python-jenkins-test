pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
            }
        }
        
        stage('Checkout') {
            steps {
                 checkout([$class: 'GitSCM', branches: [[name: 'main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/IvanGuGon1/python-jenkins-test']]])
            }
        }
        
        stage('Build') {
            steps {
                git branch: 'main', url: 'https://github.com/IvanGuGon1/python-jenkins-test'
                sh 'python3 ops.py'
            }
        }
        stage('Test') {
            steps {
                sh 'python3 -m pytest'
            }
        }
        
        
        
        
    }
}
