#!groovy​
pipeline {
  agent any
  stages{
      
    stage ('master')    {
	    steps{
		    git url: 'https://github.com/sombilat/JenkinsDemoRepo.git', branch: 'master'
			echo 'Currently within PROJ-DEV Branch'
			sh 'mvn clean package'
			sh 'mvn test'
			junit 'target/surefire-reports/*.xml'
			sh 'ls -la'
			always {
				sh 'git checkout proj-test'
			}
		}
    }

    stage ('test')
	{
        steps{
			when {
				branch 'proj-test'
			}
			sh 'git branch'			
			echo 'Currently within PROJ-TEST Branch'
			sh 'mvn clean package'
			sh 'mvn test'
			junit 'target/surefire-reports/*.xml'
			sh 'ls -la'
			always {
				sh 'git checkout proj-prod'
			}
		}
	}

    stage ('prod')
    {
		steps{
			when {
				branch 'proj-prod'
			}
			sh 'git branch'			
			echo 'Currently within PROJ-PROD Branch'
			sh 'mvn clean package'
			sh 'mvn test'
			junit 'target/surefire-reports/*.xml'
			sh 'ls -la'
		}
		
    }
  }
} 