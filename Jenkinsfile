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
                sh '''
                    VERSION=${env.BRANCH_NAME}
                    echo $VERSION
                    echo 'Complete'
                '''    
        	}	
        }
    }
}
