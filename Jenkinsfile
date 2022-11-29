pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh "java --version"
            }
        }
        stage('Test') {
            steps {
                sh "java --version"
            }
        }
        stage('Release'){
            steps {
                withCredentials([usernamePassword(credentialsId: 'backend', usernameVariable: 'USERNAME', passwordVariable: 'PASSWORD')]){
                  sh'''
                  docker login -u $USERNAME -p $PASSWORD
                  docker build -t deepadeepa/projectbackend-final:${BUILD_NUMBER} .
                  docker push deepadeepa/projectbackend-final:${BUILD_NUMBER}
                  ''' 

               
                  
           
                }
            }
        }
    }}