pipeline {
  
   agent any
    
    tools{
        maven "M3"
    }

    stages {
        stage('Clone') {
            steps {
               git ' https://github.com/NandimallaN/maven-web-app.git'
            }
        }
        stage('Build') {
            steps {
               bat 'mvn clean package'
            }
        }
        stage('docker image') {
            steps {
                bat 'docker build -t app1 .'
            }
        }
        stage('deployment') {
            steps {
                bat 'docker run -d -p 9090:8080 --name=app1c app1'
            }
        }
       
    }
}
