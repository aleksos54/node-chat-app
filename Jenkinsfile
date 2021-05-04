pipeline{
	agent any
	tools{nodejs "NodeJS"}
	stages{
	
		stage('Test'){
			steps{
				echo 'Testing'
				sh 'npma install'
				sh 'npm run test'
		}
	}
}
	post{
	
		always{
			echo 'Finished'
		}
		failure{
				echo 'Failure'
				emailext attachLog: true,
					body: "${currentBuild.currentResult}: Job ${env.JOB_NAME} build ${env.BUILD_NUMBER}",
					to: 'aleks33277@gmail.com',
					subject: "Test failed"
		}
		success{
			echo 'Success'
		}
	}
}
	
	
