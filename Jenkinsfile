pipeline {
    agent any
    stages {
        stage('vcs') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/dummyrepos/SampleWeb.git'
            }
        }
        stage('build and analysis') {
            steps {
	            mail bcc: '', body: 'Build Started', cc:'', from: '', replyTo: '', subject: 'Build Started', to: 'all@rajtech.io'
                    sh 'dotnet build SampleMVC.sln --no-incremental'
                    sh 'dotnet test SampleMVC.sln'
                    sh 'dotnet publish -c Release StudentsWeb/StudentsWeb.csproj -o published/'
		    mail bcc: '', body: 'Build Completed', cc: '', from: '', replyTo: '', subject: 'Build completed', to: 'all@rajtech.io'
                    
                }
                
            }
        }
    }
}
