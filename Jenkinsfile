pipeline {
    agent any

    stages {
        stage('scm') {
            steps {
                git 'https://github.com/UJJWALJOSHI001/jenkins_sep.git'
            }
        }
        stage('docker build') {
            steps {
                sh 'sudo docker build  -t  ashishshiv2606/pipeline:v1  . '
            }
        }
        stage('docker images') {
            steps {
                sh 'sudo docker images'
            }
        }
        stage('docker rm') {
            steps {
                sh 'sudo docker rm -f pipe1'
            }
        }
        stage('docker run') {
            steps {
                sh 'sudo docker run -d --name pipe1  -p 8099:80 ashishshiv2606/pipeline:v1'
            }
        }
        stage('docker login') {
            steps {
                sh 'sudo docker login -u ${dockerhub_username} -p ${dockerhub_password}'
            }
        }
        stage('docker push') {
            steps {
                sh 'sudo docker push ashishshiv2606/pipeline:v1'
            }
        }
        stage('print success') {
            steps {
                sh 'echo success'
            }
        }
    }
}
