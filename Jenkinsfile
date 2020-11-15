pipeline {
   agent any
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
	 stage('ejercicio_stop_pmd_check') {
	   agent {
               label "principal"
            }
           input {
                message "¿quieres que siga con el proceso?"
                ok "si claro."
                submitter "juan"
            }
	        steps {
	            bat 'mvn pmd:pmd checkstyle:checkstyle package'
            }
         }
	 stage('ejercicio_ejecutar_TP_TD_bien_error') {
	   agent {
               label "principal"
            }
           steps {
                bat 'echo "verificamos si es correcta la ejecucion"'
            }
           post { 
            success { 
                echo 'ejecucion correcta ejecutamos TP y TD'
                build job: '03-TD', parameters: [string(name: 'TD', value: 'aquí se ejecutaría TD')]
                build job: '04-TP', parameters: [string(name: 'TP', value: 'aquí se ejecutaría TP')]
            }
            failure { 
                echo 'Fallo solo ejecutamos TD'
                build job: '04-TP', parameters: [string(name: 'TP', value: 'aquí se ejecutaría TP')]
            }
        }
       }   
    }
}
