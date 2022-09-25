//SCRIPTED = In this we need nodes and stages.
node {
	
	echo "Build"
	echo "Test"
	echo "IntegraionTest"
	
}

//DECLARATIVE = in this we don't need any node we need pipeline.
pipeline {
	//agent any
	agent { docker { image 'maven:3.6.3'} } 
	stages {
		stage('Build'){
			steps{
				sh 'maven --version'
				echo "Build"
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