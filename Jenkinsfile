pipeline {
	agent {label 'master'}
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
		   sh 'rm -rf /home/zippyops/chef-repo/cookbooks/tomcat/files/*' 
                sh 'mv /jenkins/workspace/project/java-sample-app/target/*.war /chef-repo/cookbooks/tomcat/files' 
	    }
        }
    }
}
