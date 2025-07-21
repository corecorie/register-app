pipeline {
    agent { label 'jenkins-Agent' }
    tools {
        jdk 'Java17'
        maven 'Maven3'
    }
    stages{
        stage("Cleanup Workspace"){
                steps {
                cleanWs()
                }
        }

        stage("Checkout from SCM"){
                steps {
                    git branch: 'main', credentialsId: 'GitHub', url: 'https://github.com/corecorie/register-app'
                }
        }


       stage("Test Application"){
           steps {
               sh '''
        cat <<EOF > pom.xml
<project>
  <modelVersion>4.0.0</modelVersion>
  <groupId>com.example</groupId>
  <artifactId>test</artifactId>
  <version>1.0</version>
</project>
EOF
        mvn -e validate
                 sh "mvn test"
           }
       }
    }
}
