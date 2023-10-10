pipeline {
    agent any
    
    tools {
    maven 'maven'
    git 'Default'
    }
    stages {
        stage ('clone') {
            steps {
                git 'https://github.com/anitha8242/JavaWebCalculator.git'
            }
        }
        stage ('build') {
            steps {
                sh 'mvn package' 
            }
        }
        stage ('deploy') {
            steps {
                sshagent(['ec2-user']) {
         sh 'scp -o StrictHostKeyChecking=no /var/lib/jenkins/workspace/job-1/target/webapp-0.1.war ec2-user@18.217.110.59:/home/ec2-user/apache-tomcat-8.5.94/webapps'
} 
            }
        }
    }
}
