 pipeline {	
	agent any
	Tools {
	          maven 'localmaven'
	         }
	stages{
	stage('Build'){
	steps {
	sh 'mvn clean package'
	echo sh(script: 'env|sort', returnStdout: true)
	}
	post {
	success {
	echo 'Now Archiving...'
	#archiveArtifacts artifacts: '**/target/*.war'
	
	}
	}
	}
	stage ('Deploy to Staging'){
	steps {
	build job: 'Deploy-to-staging'
	}
	}
	}
	}

