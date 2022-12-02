pipeline {
    agent none
    stages {
        stage ('my build') {
            agent {label 'build'}
            steps {
                 sh 'pwd'
                 sh 'mvn package'
                 sh 'scp -r target/hello-world-war-1.0.0.war root@172.31.8.109:/opt/tomcat/webapps'
            }
        }
stage ('my deploy') {
            agent {label 'deploy'}
                steps{
                   sh 'sudo /opt/apache-tomcat-10.0.27/bin/shutdown.sh'
                   sh  'sleep 5'
                   sh 'sudo /opt/apache-tomcat-10.0.27/bin/startup.sh'
                }
            }
        }
    }
