pipeline {
		//agent any
		agent { docker {image 'maven:3.9.6'} }
		stages{
			stage('Build'){
				steps{
					sh 'mvn --version'
					echo "Build"
				}
			}
			stage('Test'){
				steps{
					echo "Test"
				}
			}
			stage('Integration Test'){
				steps{
					echo "Integration Test"
				}
			}
		}
		post {
			always {
				echo "I always run"
			}
			success{
				echo "will run on Success"
			}
			failure{
				echo "Will run on failure"
			}
		}
}
