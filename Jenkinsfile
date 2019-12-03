pipeline {
    agent { label 'master' }  
    stages {
        stage('build') {
            steps {
                checkout scm
            }
        }
        stage('post build') {
        	steps {
                VERSION=${env.BRANCH_NAME}.$(git rev-parse --short=6 HEAD).${env.BUILD_NUMBER}.$(date +%y%m%d_%H%M)
                echo $VERSION
                echo 'Complete'
        	}	
        }
    }
}
