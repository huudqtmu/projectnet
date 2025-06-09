pipeline {
 agent any
 
 enviroment {
	DOTNET_CLI_HOME ="${WORKSPACE}"
 } 
 stages {
	stage('clone'){
		steps {
			echo 'Cloning source code"
			git branch:'main', url: 'https://github.com/huudqtmu/projectnet.git'
		}
	}
	stage('restore package') {
		steps
		{
			echo 'Restore package'
			sh 'dotnet restore'
		}
	}
	stage ('build') {
		steps {
			echo 'build project netcore'
			sh 'dotnet build  --configuration Release'
		}
	}
	stage ('tests') {
		steps{
			echo 'running test...'
			sh 'dotnet test --no-build --verbosity normal'
		}
	}
	stage ('Publish') {
		steps {
			echo 'public 2 runnig folder'
			bat 'xcopy "%WORKSPACE% /E /Y /I "c:\\test1-netcore'
		}
	}
	post {
		success {
			echo 'Successful!'
		}
		failure {
			echo 'Have error when buil and run.'
		}
	}
	
  } // end stages
}//end pipeline