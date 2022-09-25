//SCRIPTED = In this we need nodes and stages.
node {
	
	echo "Build"
	echo "Test"
	echo "IntegraionTest"
	
}

//DECLARATIVE = in this we don't need any node we need pipeline.
pipeline {
	agent any 
	stages {
		stage('Build'){
			steps{
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
		sucess {
			echo 'I run when you are sucess'
		}
		failure {
			echo 'I run when you fail'
		}
	}
}