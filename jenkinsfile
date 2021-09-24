pipeline {
    agent any

    stages {
        stage('git clone ') {
            steps {
                git 'https://github.com/UJJWALJOSHI001/jenkins_sep.git'
            }
        }
        stage('docker build') {
            steps { 
                sh 'sudo docker build  -t  pipe:v1 -f Dokerfile .'
            }
        }
         stage('docker rm') {
            steps {
                sh 'sudo docker rm -f pipe1'
            }
        }
        stage('docker run') {
            steps {
                sh 'sudo docker run -d --name pipe1  -p 8082:80 pipe:v1'
            }
        }
        stage('print success') {
            steps {
                sh 'echo success'
            }
        }
    }
}
