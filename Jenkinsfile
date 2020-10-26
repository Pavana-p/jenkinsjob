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
        stage('Login to ECR'){
            steps {
		echo 'login to ECR'
		sh 'aws ecr get-login --no-include-email'
	    } 		    
        }
        stage('Push image to ECR){
	    steps {
		echo 'Push image to ECR'
		sh 'docker tag myapp:1 527858808128.dkr.ecr.ap-south-1.amazonaws.com/docker-ecr:1' 
		sh 'docker push 527858808128.dkr.ecr.ap-south-1.amazonaws.com/docker-ecr:1'
	    }	    
        }      
   }
}
