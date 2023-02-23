pipeline {
    agent any
    environment {
        PATH = "/usr/share/man/man1/mvn.1.gz:$PATH"
    }

    stages {
        stage('clone code ') {
            steps {
                git branch: 'main', credentialsId: 'git_credentials', url: 'https://github.com/Abhishek-Pandey9083/firstpipelinejob.git'
            }
        }
        
        stage('build code') {
            steps {
                sh "mvn clean install"
            }
        }
        stage('deploy code') {
            steps {
              sh "chmod 777 /var/lib/jenkins/workspace/firstjob/webapp/target/webapp.war"
                sh "cp -rf /var/lib/jenkins/workspace/firstjob/webapp/target/webapp.war /var/lib/tomcat9/webapps/"
            }
        }
        
    }
}
