pipeline {
 agent any
 
 stages {
	stage('clone'){
		steps {
			echo 'Cloning source code'
			git branch:'main', url: 'https://github.com/huudqtmu/projectnet.git'
		}
	}
	stage('restore package') {
		steps
		{
			echo 'Restore package'
			bat 'dotnet restore'
		}
	}
	stage ('build') {
		steps {
			echo 'build project netcore'
			bat 'dotnet build  --configuration Release'
		}
	}
	stage ('tests') {
		steps{
			echo 'running test...'
			bat 'dotnet test --no-build --verbosity normal'
		}
	}
	stage ('Publish') {
		steps {
			echo 'public 2 runnig folder'
			bat 'xcopy "%WORKSPACE% /E /Y /I "c:\\test1-netcore'
		}
	}
  } // end stages
}//end pipeline