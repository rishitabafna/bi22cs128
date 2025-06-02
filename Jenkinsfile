pipeline{
	agent any
	tools{
		maven 'Maven'
	}
	stages{
		stage('a'){
			steps{
				git branch: 'master' url:'https://github.com/rishitabafna/bi22cs128.git'
			}
		}		
		stage('b'){
			steps{
				sh 'mvn clean package'
			}
		}
		stage('c'){
			steps{
				sh 'mvn test'
			}
		}
		stage('d'){
			steps{
				sh 'java -jar target/bi22cs128-1.0-SNAPSHOT.jar'
			}
		}
	}
	post{
		success{
			echo 'Build  and deployed successfully'
		}
		failure{
			echo 'Build failed'
		}
	}
}
