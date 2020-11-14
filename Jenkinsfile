pipeline {
   agent none
    stages {
	stage('ejercicio') {
	    agent {
               label "principal"
            }
           steps {
	      git '${git}'
	   }
	   steps {
              bat 'java -version'
	   }
       }
    }
}
