pipeline {
   agent none
    stages {
	stage('Non-Parallel Stage') {
	    agent {
                        label "principal"
                }
        steps {
                echo 'prueba para ver si funciona cogiendo desde el archivo'
                }
        }
    }
}
