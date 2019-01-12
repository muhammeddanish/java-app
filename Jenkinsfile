pipeline {
	agent {node 'master'}
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
                sh 'mv /home/zippyops/jenkins/workspace/project/java-sample-app/target/* /home/zippyops/chef-repo/cookbooks/tomcat/files' 
	    }
        }
    }
}
