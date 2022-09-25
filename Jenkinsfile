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
	
}