pipeline {
    agent any
    tools{
        jdk 'java'
        maven 'maven'
    }
    stages {
        stage('git'){
            steps{
                git 'https://github.com/urc1712/WebApp.git'
            }
        }
        stage('maven'){
            steps{
                sh 'mvn clean package'
            }
        }
        stage('deploy'){
            steps{
                deploy adapters: [tomcat9(credentialsId: '7092b0ee-0800-469f-a08a-f44e91e1c01b', path: '', url: 'http://3.17.206.171:8080/')], contextPath: 'myweb', war: '**/*war'
            }
        }
        
    }
}
