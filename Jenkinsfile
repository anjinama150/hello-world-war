pipeline {
    agent none
    stages {
        stage ('build') {
            agent {label 'jenkins'}
            steps {
                 sh 'pwd'
                 sh 'mvn package'
                 sh 'hello-world-war'
                 sh 'cp -r hello-world-war-1.0.0.war /opt/apache-tomcat-10.0.27/webapps jenkin@172.31.2.54:/opt/tomcat/webapps'
            }
        }
stage ('deploy') {
            agent {label 'jenkin'}
                steps{
                   sh 'sudo /opt/apache-tomcat-10.0.27/bin/shutdown.sh'
                   sh  'sleep 5'
                   sh 'sudo /opt/apache-tomcat-10.0.27/bin/startup.sh'
                }
            }
        }
    }
