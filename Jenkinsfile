//jenkins pipeline
pipeline{
    agent any
    stages{
        stage("git clone"){
            steps{
                git 'https://github.com/pavanvarikolu/springloginpage.git'
            }
        }
        stage("maven build"){
            steps{
                bat 'mvn clean install'
            }
        }
        stage("deploy to tomcat"){
            steps{
                deploy adapters: [tomcat9(credentialsId: 'Tomcat-Credentials', path: '', url: 'http://localhost:8080/')], contextPath: null, war: '**/*.war'
            }
        }
    }
}