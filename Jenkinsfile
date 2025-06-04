pipeline{
	agent any
	tools{
		maven 'Maven'
	}
	stages{
		stage('Checkout'){
			steps{
				git branch:'master',url:'https://github.com/akussuto/Ext1.git'
			}
		}
		stage('Build'){
			steps{
				sh 'mvn clean package'
			}
		}
		stage('Test'){
			steps{
				sh 'mvn test'
			}
		}
		stage('Run-Application'){
			steps{
				sh 'java -jar target/SNAPSHOT-1.0-jar'
			}
		}
	}
	post{
		success{
			echo 'Build successful'
		}
		failure{
			echo 'Build failed'
		}
	}
}
