pipeline {
    agent any
    stages {
        stage('Code') {
            steps {
               sh 'rm -rf docker-sravia'
               sh 'git clone --branch features https://github.com/Sravia94/docker-sravia'
               sh 'cd docker-sravia' 
            }
        }
        stage('Build') {
            steps {
                sh 'chmod 777 steps.sh'
                sh 'ls -l'
                sh 'steps.sh'
                sh 'docker-compose up -d'
            }
        }
        
       
    }
}
