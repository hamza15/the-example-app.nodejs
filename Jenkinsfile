pipeline {
    agent { label 'master' }  
    
    tools {nodejs 'node'}
    
    stages {
        stage('build') {
            steps {
                checkout scm
            }
        }
        stage('post build') {
        	steps {
                sh '''
                    VERSION=${BRANCH_NAME}.$(git rev-parse --short=6 HEAD).${BUILD_NUMBER}.$(date +%y%m%d_%H%M)
                    GIT_COMMIT=$(git log -1 --pretty=format:%h:%aE:%s):::${VERSION}
                    echo "Git commit is ${GIT_COMMIT}"
                    echo "Image tag is :: ${VERSION}"
                    
                '''    
        	}	
        }
        stage('Test NPM') {
            steps {
                sh '''
                   npm -v
                '''
            }
        }
        stage('Test Node') {
            steps {
                sh '''
                   node -v
                '''
            }
        }
        stage('Test Envrionment Variables') {
            steps {
                sh '''
                   echo ${VERSION}
                '''
            }
        }
    }
}
