pipeline {
	agent any


	tools {
		// Install the Maven version configured as "M3" and add it to the path. Demo comment
		maven "maven"
		jdk "java"
	}


	stages {
		stage('Build'){
			steps{
				// Get some code from Github Repository
				git 'https://github.com/mihirkp/tomcat_pipeline.git'

				//Run MAven on a Unix agent.
				//sh "mvn -Dmaven.test.failure.ignore=true clean package"

				//To run Maven on a Windows agent, use
				bat "mvn -Dmaven.test.failure.ignore=true clean package"

			}
		}
	}
}
