//SCRIPTED = In this we need nodes and stages.
node {
	
	echo "Build"
	echo "Test"
	echo "IntegraionTest"
	
}

//DECLARATIVE = in this we don't need any node we need pipeline.
pipeline {
	agent any
	//agent { docker { image 'maven:3.6.3'} } 
	enviroment {
		dockerHome = tool 'myDocker'
		mavenHome = tool 'myMaven'
		PATH = "$dockerHome/user:$mavenHome/user:$PATH"
	}
	stages {
		stage('Build'){
			steps{
				sh 'mvn --version'
				sh 'docker version'
				echo "Build"
				echo "PATH - $PATH"
				echo "BUILD_NUMBER - $env.BUILD_NUMBER"
				echo "BUILD_ID - $env.BUILD_ID"
				echo "JOB_NAME - $env.JOB_NAME"
				echo "BUILD_TAG - $env.BUILD_TAG"
				echo "BUILD_URL - $env.BUILD_URL"
			}
		}
		stage('Test'){
			steps{
				echo "Test"
			}
		}
		stage('IntegraionTest'){
			steps{
				echo "IntegraionTest"
			}
		}	
	}
	
	post {
		always {
			echo 'I am awsome. I run always'
		}
		success {
			echo 'I run when you are success'
		}
		failure {
			echo 'I run when you fail'
		}
	}
}