#!groovy​
pipeline {
agent any
  stages{
	git url: 'https://github.com/sombilat/JenkinsDemoRepo.git', branch: 'master'
    stage ('master')    {
	    steps{
			echo 'Currently within PROJ-DEV Branch'
			sh 'mvn test'
			sh 'ls -la'
			sh 'git checkout test'
		}
    }

    stage ('test')
	{
        steps{
			when {
				branch 'test'
			}
			sh 'git branch'			
			echo 'Currently within PROJ-TEST Branch'
			sh 'mvn clean package'
			sh 'ls -la'
			always {
				sh 'git checkout prod'
			}
		}
	}

    stage ('prod')
    {
		steps{
			when {
				branch 'prod'
			}
			sh 'git branch'			
			echo 'Currently within PROJ-PROD Branch'
			sh 'mvn clean package'
			sh 'ls -la'
		}
		
    }
  }
} 