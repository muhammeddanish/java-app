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
		   sh 'rm -rf /home/zippyops/chef-repo/cookbooks/apache_tomcat/files/*' 
                sh 'mv /home/zippyops/jenkins/workspace/upstream project/java-sample-app/target/*.war /home/zippyops/chef-repo/cookbooks/apache_tomcat/files' 
	    }
        }
    }
}
