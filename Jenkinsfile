pipeline {
    agent none
    stages {
        stage ('build') {
            agent {label 'slaveone'}
            steps {
                 sh 'pwd'
                 sh 'mvn package'
                 sh 'cp -r hello-world-war-1.0.0.war /opt/apache-tomcat-10.0.27/webapps slavetwo@172.31.2.54:/opt/tomcat/webapps'
            }
        }
stage ('deploy') {
            agent {label 'slavetwo'}
                steps{
                   sh 'sudo /opt/apache-tomcat-10.0.27/bin/shutdown.sh'
                   sh  'sleep 5'
                   sh 'sudo /opt/apache-tomcat-10.0.27/bin/startup.sh'
                }
            }
        }
    }
