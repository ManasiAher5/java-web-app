pipeline{
    agent any
    stages{
        stage('checkout code') {
            steps {
                git branch:'main', url:'https://github.com/ManasiAher5/java-web-app.git'
            }
        }
        stage('build code') {
            steps {
               sh '/opt/maven/bin/mvn clean package' 
            }
        }
        stage('deploy code') {
            steps {
                deploy adapters:[tomcat9(url:'http://3.109.202.152:8080', credentialsId:'tomcat-cred')], war:'target/*.war'
            }
        }    
    }
 }
