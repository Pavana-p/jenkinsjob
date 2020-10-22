pipeline {
    agent any
    tools {
        jdk 'jdk1.8'
	maven 'maven3'
    }
    stages {
        stage('pull repo'){
	    steps {
	        git 'https://github.com/Pavana-p/jenkinsjob.git'
            }
	}
	stage('build artifactry'){
	    steps {
	        sh 'mvn clean'
		sh 'mvn install'
	    }
	}
    }
}

