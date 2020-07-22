pipeline {
	agent {label 'jenkins-docker'}
	stages {
		stage('Build') {
			steps {
			    container('docker') {
				    sh "echo Hello world"
				    sh "docker build -t go-demo ."
			    }
			    
			}
		}
	}
}