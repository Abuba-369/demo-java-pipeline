pipeline {
    agent any
	tools {
    maven 'M3'
  }
	
    stages {
        stage ('checkout') {
            steps {
		checkout scm
            }
        }
          stage ('Build') {
             steps {
                sh '${m2_home}/var/lib/jenkins/tools/hudson.tasks.Maven_MavenInstallation/M3/bin/mvn -f java-sample-app/pom.xml clean install' 
            }
	    
        }
    stage ('Deploy') {
             steps {
               sh 'scp  ${WORKSPACE}/java-sample-app/target/java-sample-app-1.0.0.war root@192.168.43.222:/opt/tomcat/apache-tomcat-9.0.41/webapps/'
	       // sh 'cd'		     
               // sh 'sudo cp -r {WORKSPACE}/test-pipeline/java-sample-app/target/java-sample-app-1.0.0.war /opt/tomcat/tomcat-9.0.30/webapps/'		     
	       // sh 'sudo cp -r /var/lib/jenkins/workspace/test-pipeline/java-sample-app/target/java-sample-app-1.0.0.war /opt/tomcat/tomcat-9.0.30/webapps/'		      
            }
	    
    //this is test....
    }
	
}
}
