pipeline {
		agent any
		//agent { docker {image 'maven:3.9.6'} }
		environment{
			dockerHome = tool 'mydocker'
			mavenHome = tool 'mymaven'
			PATH = "$dockerHome/bin:$mavenHome/bin:$PATH"
		}

		stages{
			stage('Checkout'){
				steps{
					sh 'mvn --version'
					sh 'docker version'
					echo "Build"
					echo "$PATH"
					echo "BUILD_NUMBER - $env.BUILD_NUMBER"
					echo "Build ID - $env.BUILD_ID"
					echo "Job Name - $env.JOB_NAME"
					echo "Build Tag - $env.BUILD_TAG"
					echo "Build URL - $env.BUILD_URL"
				}
			}
			stage('Compile'){
				steps{
					sh "mvn clean complete"
				}
			}
			stage('Test'){
				steps{
					sh "mvn Test"
				}
			}
			stage('Integration Test'){
				steps{
					sh "mvn failsafe:integration-test failsafe:verify"
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
