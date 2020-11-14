pipeline {
   agent none
    stages {
	stage('ejercicio') {
	    agent {
               label "principal"
            }
           
	   steps {
              bat 'mvn --version'
	   }
       }
    }
}
