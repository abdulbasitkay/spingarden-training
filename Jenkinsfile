pipeline {
	agent {label 'jenkins-go'}
	stages {
		stage('Build') {
			steps {
			    container('golang') {
				    sh "echo Hello world"
				    sh "go version"
			    }
			}
		}
	}
}