pipeline {
		agent any
		//agent { docker {image 'maven:3.9.6'} }
		environment{
			dockerHome = tool 'mydocker'
			mavenHome = tool 'mymaven'
			PATH = "$dockerHome/bin:$mavenHome/bin:$PATH"
		}

		stages{
			stage('Build'){
				steps{
					sh 'mvn --version'
					sh 'docker version'
					echo "Build"
					echo "$PATH"
					echo "BUILD_NUMBER - $env.BUILD_NUMBER"
					echo "$env.BUILD_ID"
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
