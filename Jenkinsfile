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
			sh 'cat src/main/Class/MainClass.java'
			sh 'javac -d . src/main/Class/MainClass.java'
			sh 'java main.Class.MainClass'
			sh 'git checkout test'
		}
    }

    stage ('test')
	{
        steps {
			sh 'git branch'			
			echo 'Currently within PROJ-TEST Branch'
			sh 'mvn test'
			sh 'ls -la'
			sh 'cat src/main/Class/MainClass.java'
			sh 'javac -d . src/main/Class/MainClass.java'
			sh 'java main.Class.MainClass'
			sh 'git checkout prod'
		}
	}

    stage ('prod')
    {
		steps{
			sh 'git branch'			
			echo 'Currently within PROJ-PROD Branch'
			sh 'mvn test'
			sh 'ls -la'
			sh 'cat src/main/Class/MainClass.java'
			sh 'javac -d . src/main/Class/MainClass.java'
			sh 'java main.Class.MainClass'
			sh 'cat src/main/Class/MainClass.java'
		}
		
    }
  }
} 