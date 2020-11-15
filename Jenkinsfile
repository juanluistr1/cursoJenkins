pipeline {
   agent none
   tools {
        maven 'LocalMaven' 
        jdk 'LocalJDK8'
    }
    stages {
	 stage('ejercicio_git') {
	    agent {
               label "principal"
            }
	    steps {
	        git '${git}'
			bat 'mvn --version'
            bat 'java -version'
		    bat 'mvn pmd:pmd checkstyle:checkstyle package'
        }
     }  
    }
}
