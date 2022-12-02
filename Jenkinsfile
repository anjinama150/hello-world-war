pipeline {
    agent none
    stages {
        stage ('my build') {
            agent {label 'build'}
            steps {
                 sh 'pwd'
                 sh 'mvn package'
                 sh 'scp -r /home/jenkins/workspace/tomcat_deploy/hello-world-war/target/hello-world-war-1.0.0.war root@172.31.8.109:/opt/tomcat/webapps'
            }
        }
        stage (' my deploy') {
            agent {label 'deploy'}
                steps{
                   sh 'sudo sh /opt/tomcat/bin/startup.sh'
                }
            }
        }
    }
