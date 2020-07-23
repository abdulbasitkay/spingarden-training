pipeline {
	agent {label 'jenkins-docker'}
	stages {
		stage('Build') {
			steps {
			    container('docker') {
				    sh "echo Hello world Spinnaker"
				    sh "docker build -t carvanit/go-demo:latest ."
			    }
			    
			}
		}
		stage('Publish') {
			steps {
			    container('docker') {
				    withCredentials([usernamePassword(credentialsId: 'dockerhub', passwordVariable: 'PASS', usernameVariable: 'USER')]) {
				    	sh "docker login -u ${USER} -p ${PASS}"
				    	sh "docker push carvanit/go-demo:latest"
					}
			    }
			    
			}
		}
	}
}