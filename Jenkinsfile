pipeline {
    agent none
    stages {
        stage ('my build') {
            agent {label 'build'}
            steps {
                 sh 'pwd'
                 sh 'sudo apt install maven -y'
                 sh 'mvn package'
                 sh 'sudo cp -r hello-world-war-1.0.0.war /opt/apache-tomcat-10.0.27/webapps jenkin@172.31.2.54:/opt/tomcat/webapps'
            }
        }
stage ('my deploy') {
            agent {label 'builder'}
                steps{
                   sh 'sudo /opt/apache-tomcat-10.0.27/bin/shutdown.sh'
                   sh  'sleep 5'
                   sh 'sudo /opt/apache-tomcat-10.0.27/bin/startup.sh'
                }
            }
        }
    }
