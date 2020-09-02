pipeline {
    agent any

    stages {
        stage('preparation') {
            steps {
                git 'https://github.com/ananyapanchan05/certification_poject.git'
            }
        }
		stage('build docker image'){
			steps{ 
		          bat """
			  cd C:/Windows/System32/config/systemprofile/AppData/Local/Jenkins.jenkins/workspace/phpbasic
			  docker build -t phpbasic:v1 .
			  """
			
			}
		}
		stage('Run docker image'){
			steps{
		    bat docker run -d -p 9090:80 phpbasic:v1

			}
		}
    }
}
