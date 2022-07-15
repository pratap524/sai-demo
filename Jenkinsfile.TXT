pipeline {
	agent any
	stages {
		stage('clone the code'){
			steps {
		sh "git clone https://github.com/pratap524/gamtkart2" 
		}
		}

		stage(build) {
			steps {
		sh "mvn install"
	               }
	               }
		stage(deploy) {
		steps {
		sh "scp -r /taget/gamutgurus.war gamut@172.17.0.3:/home/project/apache-tomcat-/webapps" 
			}
			}
		}
		}
