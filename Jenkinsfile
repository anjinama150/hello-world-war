pipeline {
    agent agent { label 'build' }
    stages {
        stage('my Build') {
            steps {
              sh 'mvn package'
            }
        }
      stage ( 'my deploy' ) {
        agent { label 'builder' }
        steps {
             sh 'cd target'
             sh 'sudo cp -R hello-world-war-1.0.0.war /opt/apache-tomcat-10.0.27/webapps/'
             sh 'sudo /opt/apache-tomcat-10.0.27/bin/shutdown.sh'
             sh 'sleep 5'
             sh 'sudo sh /opt/apache-tomcat-10.0.27/bin/startup.sh'
        }
      }
    }
}
