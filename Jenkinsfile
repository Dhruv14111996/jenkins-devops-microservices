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
	environment {
		dockerHome = tool 'myDocker'
		mavenHome = tool 'myMaven'
		PATH = "$dockerHome/bin:$mavenHome/bin:$PATH"
	}
	stages {
		stage('Checkout') {
			steps {
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
		stage('Compile') {
			steps {
				sh "mvn clean compile"
			}
		}
		stage('Test') {
			steps {
				sh "mvn test"
			}
		}
		stage('IntegraionTest') {
			steps {
				sh "mvn failsafe:integration-test failsafe:verify"
			}
		}
		stage('Package') {
			steps {
				sh "mvn package -DskipTests"
			}
		}
		
		stage('Build Docker Image') {
			steps {
				//"docker build -t dhruv1411/currency-exchange:$env.BUILD_TAG"
				script {
					dockerImage = docker.build("dhruv1411/currency-exchange:${env.BUILD_TAG}")
				}
			}
		}
		
		stage Logs('Push Docker Image') {
			steps {
				script {
					docker.withRegistry(' ', 'dockerhub') {
						dockerImage.push();
						dockerImage.push('latest');
					}
				}
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