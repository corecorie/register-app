pipeline {
    agent { label 'jenkins-Agent' }
    tools {
        jdk 'Java17'
        maven 'Maven3'
    }
    stages{

        stage("Checkout from SCM"){
                steps {
                    git branch: 'main', credentialsId: 'GitHub', url: 'https://github.com/corecorie/register-app'
                }
        }


       stage("Test Application"){
           steps {
            
                 sh "mvn test"
           }
       }
    }
}
