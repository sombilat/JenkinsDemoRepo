#!groovy​
pipeline {
<<<<<<< HEAD
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
=======
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
>>>>>>> master
			}
		}
    }

    stage ('test')
	{
<<<<<<< HEAD
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
=======
        steps {
			sh 'git branch'			
			echo 'Currently within PROJ-TEST Branch'
			sh 'mvn clean package'
			sh 'ls -la'
			always {
				sh 'git checkout prod'
>>>>>>> master
			}
		}
	}

    stage ('prod')
    {
		steps{
<<<<<<< HEAD
			when {
				branch 'proj-prod'
			}
			sh 'git branch'			
			echo 'Currently within PROJ-PROD Branch'
			sh 'mvn clean package'
			sh 'mvn test'
			junit 'target/surefire-reports/*.xml'
=======
			sh 'git branch'			
			echo 'Currently within PROJ-PROD Branch'
			sh 'mvn clean package'
>>>>>>> master
			sh 'ls -la'
		}
		
    }
  }
} 