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
        		sh 'node -v'
                echo 'Complete'
        	}	
        }
    }
}
