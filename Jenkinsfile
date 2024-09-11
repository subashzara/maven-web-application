node{
properties([pipelineTriggers([pollSCM('* * * * *')])])
def mavenHome = tool name: "maven3.9.8"
	stage('checkout'){
	git branch: 'master', credentialsId: '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', url: 'https://github.com/subashzara/maven-web-application.git'
	}
	stage('build'){
	sh "${mavenHome}/bin/mvn clean package"
	}
	/*
	stage('sonarqube'){
	sh "${mavenHome}/bin/mvn clean sonar:sonar"
	}
	stage('nexus'){
	sh "${mavenHome}/bin/mvn clean deploy"
	}
	stage('deploy in tomcat'){
	sshagent(['7aef4290-dc7d-497d-8be3-20f605fdc75b']) {
	   	sh "scp -o StrictHostKeyChecking=no target/maven-web-application.war ec2-user@3.111.29.254:/opt/apache-tomcat-9.0.93/webapps/"
	}
	}*/
}//nodeclosing
