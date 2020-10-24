pipeline {
    agent any
    tools {
        jdk 'jdk1.8'
	maven 'maven3'
    }
    stages {
        stage('pull repo'){
	    steps {
	        echo 'Pull repo from github master branch'
		git 'https://github.com/Pavana-p/jenkinsjob.git'
            }
	}
	stage('build artifactry'){
	    steps {
	        echo 'clean & install artifactry'
		sh 'mvn clean'
	        sh 'mvn install'
	    }
	}
	stage('build docker image'){
	    steps {
	        echo 'build docker image'
		sh 'docker build -t myimage:1 .'
	    }
	}    
    }
}

