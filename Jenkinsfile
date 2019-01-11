pipeline {
    agent any
    stages {
        stage ('checkout') {
            steps {
		checkout scm
            }
        }
        stage ('Build') {
            steps {
                sh 'mvn -f java-sample-app/pom.xml clean install' 
	    }
        }
	     stage ('copy') {
            steps {
                sh 'rm -rf /chef-repo/cookbooks/tomcat/files/*' 
                sh 'cp /home/zippyops/jenkins/workspace/project/java-sample-app/target/java-sample-app-1.0.0.war /root/chef-repo/cookbooks/tomcat/files' 
	    }
        }
    }
}
