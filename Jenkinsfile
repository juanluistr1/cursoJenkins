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
        }
     }
		stage('ejercicio_mavem') {
 	    agent {
               label "principal"
            }
	    steps {
                bat 'mvn --version'
                bat 'java -version'
            }
         }  	 
    }
}
