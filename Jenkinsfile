pipeline {
	agent any
	tools{
		maven "maven-3.9.6"
	}
	stages{
		stage('git checkout'){
			steps{
				git branch: 'dev', url: 'https://github.com/kkdevopsmani/maven-webapplication-project-kkfunda.git'
			}
		}
		stage('compile'){
			steps{
				sh "mvn compile"
			}
		}
		stage('Build'){
			steps{
				sh "mvn clean package"
			}
		}
		stage('Nexus Deploy)'{
			steps{
				sh "mvn clean deploy"
			}
		}
		stage('Tomcat Deploy'){
			steps{
				sh """
				curl -u admin:ManiHasini#153 --upload-file /var/lib/jenkins/workspace/scripted-way-PL-1/target/maven-web-application.war \
"http://3.110.104.66:8080/manager/text/deploy?path=/maven-web-application&update=true"
"""
			}
		}
			  }
			  }
			  
			  
