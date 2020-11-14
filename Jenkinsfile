pipeline {
   agent none
    stages {
	stage('Non-Parallel Stage') {
	    agent {
                        label "principal"
                }
        steps {
                git '${git}'
                }
        }
    }
}
