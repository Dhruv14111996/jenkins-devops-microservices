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
		stages('Build'){
			steps{
				echo "Build"
			}
		}
	stages {
		stages('Test'){
			steps{
				echo "Test"
			}
		}
	stages {
		stages('IntegraionTest'){
			steps{
				echo "IntegraionTest"
			}
		}	
	}
	
}