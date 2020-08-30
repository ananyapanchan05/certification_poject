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
			 sh '''#!/bin/bash
			  echo 'inside bash'
			  echo 'building docker image'
			  cd C:/Windows/System32/config/systemprofile/AppData/Local/Jenkins.jenkins/workspace/php_project
			  sudo -n docker build -t phpbasic:v1 .
			 '''
			}
		}
		stage('Run dokcer image'){
			steps{
			sh '''#!/bin/bash
			echo 'running docker image'
		    sudo docker run -d -p 9090:80 phpbasic:v1
			echo 'application deployed' 
			'''
			}
		}
    }
}
