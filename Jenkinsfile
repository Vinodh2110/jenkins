pipeline {
		agent any
		stages{
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
