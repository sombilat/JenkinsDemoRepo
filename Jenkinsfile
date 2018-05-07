#!groovy​
pipeline {
agent any
  stages{
	
    stage ('master')    {
	    steps{
	    	git url: 'https://github.com/sombilat/JenkinsDemoRepo.git', branch: 'master'
			echo 'Currently within PROJ-DEV Branch'
			sh 'mvn test'
			sh 'ls -la'
			always {
				sh 'git checkout test'
			}
		}
    }

    stage ('test')
	{
        steps {
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
			sh 'git branch'			
			echo 'Currently within PROJ-PROD Branch'
			sh 'mvn clean package'
			sh 'ls -la'
		}
		
    }
  }
} 